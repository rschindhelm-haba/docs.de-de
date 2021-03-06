---
title: Überblick über die Interoperabilität – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
ms.openlocfilehash: 160403b938a95ae5bb03703f73fa906de5fc3ded
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410757"
---
# <a name="interoperability-overview-c-programming-guide"></a>Überblick über die Interoperabilität (C#-Programmierhandbuch)
Dieses Thema beschreibt Methoden zur Gewährleistung der Interoperabilität zwischen von C#-verwaltetem und nicht verwaltetem Code.  
  
## <a name="platform-invoke"></a>Plattformaufruf  
 Der *Plattformaufruf* ist ein Dienst, durch den verwalteter Code nicht verwaltete Funktionen aufrufen kann, die in DLLs (Dynamic Link Library) implementiert sind, z.B. die in der Microsoft Windows-API enthaltenen Funktionen. Es sucht eine exportierte Funktion, ruft diese auf und marshallt ihre Argumente (ganze Zahlen, Zeichenfolgen, Arrays, Strukturen usw.) bei Bedarf über die Grenzen des dialogfähigen Betriebs hinaus.  
  
 Weitere Informationen finden Sie unter [Verwenden nicht verwalteter DLL-Funktionen](../../../framework/interop/consuming-unmanaged-dll-functions.md) und [Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).  
  
> [!NOTE]
>  Die [Common Language Runtime](../../../standard/clr.md) (CLR) verwaltet den Zugriff auf Systemressourcen. Das Aufrufen von nicht verwaltetem Code, der sich außerhalb der CLR befindet, umgeht diesen Sicherheitsmechanismus; deshalb stellt er ein Sicherheitsrisiko dar. Nicht verwalteter Code kann z.B. Ressourcen in nicht verwaltetem Code direkt aufrufen und umgeht damit die Sicherheitsmechanismen der CLR. Weitere Informationen finden Sie unter [Sicherheit in .NET](../../../standard/security/index.md).  
  
## <a name="c-interop"></a>C++ Interop  
 Sie können C++ Interop – auch als It Just Works (IJW) bezeichnet – verwenden, um ein native C++-Klasse zu umschließen, sodass diese von in C# oder in einer anderen .NET Framework-Programmiersprache geschriebenem Code genutzt werden kann. Dafür schreiben Sie C++-Code, der eine native DLL- oder COM-Komponente umschließen kann. Im Gegensatz zu anderen .NET-Programmiersprachen verfügt [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] über eine Interoperabilitätsunterstützung, dank der verwalteter und nicht verwalteter Code in derselben Anwendung und sogar in derselben Datei verwendet werden können. Anschließend erstellen Sie den C++-Code mithilfe des **/clr**-Compilerschalters, um eine verwaltete Assembly zu erzeugen. Zuletzt fügen Sie der Assembly in Ihrem C#-Projekt einen Verweis hinzu und verwenden das umschlossene Objekt genauso wie eine andere verwaltete Klasse.  
  
## <a name="exposing-com-components-to-c"></a>Verfügbarmachen von COM-Komponenten in C\#
 Sie können eine COM-Komponente aus einem C#-Projekt nutzen. Dies sind die Hauptschritte:  
  
1.  Suchen Sie eine COM-Komponenten, die Sie verwenden möchten, und registrieren Sie diese. Verwenden Sie „regsvr32.exe“ zur Registrierung und Aufhebung der Registrierung einer COM-DLL.  
  
2.  Fügen Sie dem Projekt einen Verweis auf eine COM-Komponente oder eine Typbibliothek hinzu.  
  
     Beim Hinzufügen des Verweises verwendet Visual Studio [Tlbimp.exe (das Type Library Importer-Tool)](../../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), das eine Typbibliothek als Eingabe akzeptiert, um eine .NET Framework-Interopassembly auszugeben. Die Assembly – auch als Runtime Callable Wrapper (RCW) bezeichnet – enthält verwaltete Klassen und Schnittstellen, die die COM-Klassen und -Schnittstellen umschließen, die sich in der Typbibliothek befinden. Visual Studio fügt dem Projekt einen Verweis auf die generierte Assembly hinzu.  
  
3.  Erstellen Sie eine Instanz einer im RCW definierten Klasse. Dadurch wird wiederum eine Instanz des COM-Objekts erstellt.  
  
4.  Verwenden Sie das Objekt genauso, wie Sie andere verwaltete Objekte verwenden. Wenn das Objekt von der automatische Speicherbereinigung freigegeben wird, wird auch die Instanz des COM-Objekts aus dem Speicher freigestellt.  
  
 Weitere Informationen finden Sie unter [Verfügbarmachen von COM-Komponenten für .NET Framework](../../../../docs/framework/interop/exposing-com-components.md).  
  
## <a name="exposing-c-to-com"></a>Verfügbarmachen von C# für COM  
 COM-Clients können C#-Typen nutzen, die ordnungsgemäß verfügbar gemacht wurden. Dies sind die grundlegenden Schritte für das Verfügbarmachen von C#-Typen:  
  
1.  Fügen Sie Ihrem C#-Projekt Interop-Attribute hinzu.  
  
     Durch das Ändern der Visual C#-Projekteigenschaften können Sie eine Assembly für COM sichtbar machen. Weitere Informationen finden Sie unter [Dialogfeld „Assemblyinformationen“](/visualstudio/ide/reference/assembly-information-dialog-box).  
  
2.  Generieren Sie eine COM-Typbibliothek, und registrieren Sie diese für den Gebrauch mit COM.  
  
     Sie können die Visual C#-Projekteigenschaften so modifizieren, dass die C#-Assembly automatisch für COM-Interop registriert wird. Visual Studio verwendet [Regasm.exe (das Assembly Registration-Tool)](../../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) mithilfe des Befehlszeilenschalters `/tlb`, das die verwaltete Assembly als Eingabe akzeptiert, um eine Typbibliothek zu generieren. Diese Typbibliothek beschreibt den Typ `public` in der Assembly und fügt Verzeichniseinträge hinzu, um COM-Clients das Erstellen verwalteter Klassen zu ermöglichen.  
  
 Weitere Informationen finden Sie unter [Verfügbarmachen von .NET Framework-Komponenten in COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md) und [COM-Beispielklasse](../../../csharp/programming-guide/interop/example-com-class.md).  
  
## <a name="see-also"></a>Siehe auch

- [Improving Interop Performance (Optimieren der Interopleistung)](https://docs.microsoft.com/previous-versions/msp-n-p/ff647812%28v=pandp.10%29)
- [Einführung in die Interoperabilität zwischen COM und .NET](/office/client-developer/outlook/pia/introduction-to-interoperability-between-com-and-net)
- [Einführung in COM-Interop (Visual Basic)](../../../../docs/visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
- [Marshaling between Managed and Unmanaged Code (Marshalling zwischen verwaltetem und nicht verwaltetem Code)](../../../../docs/framework/interop/interop-marshaling.md)
- [Interoperabilität mit nicht verwaltetem Code](../../../../docs/framework/interop/index.md)
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
