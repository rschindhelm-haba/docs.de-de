---
title: XAML-Namespaces und Namespacezuordnung für WPF-XAML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom classes [WPF], mapping namespaces to
- XAML [WPF], namespaces
- namespace mapping [WPF]
- assemblies [WPF], mapping namespaces to
- mapping namespaces [WPF]
- XAML [WPF], namespace mapping
- classes [WPF], mapping namespaces to
- namespaces [WPF]
ms.assetid: 5c0854e3-7470-435d-9fe2-93eec9d3634e
ms.openlocfilehash: cf09415e9203c82d26bccf4e84db5607047b6f35
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176916"
---
# <a name="xaml-namespaces-and-namespace-mapping-for-wpf-xaml"></a>XAML-Namespaces und Namespacezuordnung für WPF-XAML
Diesem Thema bietet weitere Erläuterungen zu Vorhandensein und Zweck der beiden XAML-Namespacezuordnungen, die häufig im Stammelement einer WPF XAML-Datei zu finden sind. Es wird ebenfalls beschrieben, wie Sie ähnliche Zuordnungen für Elemente in Ihrem eigenen Code und/oder separaten Assemblys erstellen können.  

## <a name="what-is-a-xaml-namespace"></a>Was ist ein XAML-Namespace?  
 Ein XAML-Namespace ist eine Erweiterung des Konzepts eines XML-Namespaces. Die Techniken zum Angeben eines XAML-Namespaces basieren auf der XML-Namespace-Syntax, der Konvention für die Verwendung von URIs als Namespacebezeichner, der Verwendung von Präfixen als Mittel zur Referenzierung mehrerer Namespaces aus derselben Markupquelle und so weiter. Das primäre Konzept, das der XAML-Definition des XML-Namespaces hinzugefügt wird, ist, dass ein XAML-Namespace einen eindeutigen Bereich für Markupverwendungen schafft und außerdem beeinflusst, wie Markupentitäten potenziell von bestimmten CLR-Namespaces und referenzierten Assemblys unterstützt wird. Letzteres wird auch durch das Konzept eines XAML-Schemakontexts beeinflusst. Was die Funktionsweise von WPF mit XAML-Namespaces angeht, reicht es jedoch, von XAML-Namespaces als die Kombination aus einem standardmäßigen XAML-Namespace, dem XAML-Sprachnamespace und weiteren, für die direkte Zuordnung von XAML-Markup zu bestimmten unterstützenden CLR-Namespaces und referenzierten Assemblys XAML-Namespaces verwendeten XAML-Namespaces zu reden.  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>   
## <a name="the-wpf-and-xaml-namespace-declarations"></a>Deklarationen der WPF- und XAML-Namespaces  
 Innerhalb der Namespacedeklarationen im Stammelement vieler XAML-Dateien sehen Sie, dass in der Regel zwei XML-Namespacedeklarationen vorhanden sind. Die erste Deklaration ordnet den gesamten WPF-Client/Framework-XAML-Namespace als Standard zu:  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 Die zweite Deklaration ordnet einen separaten XAML-Namespace (normalerweise) dem `x:`-Präfix zu.  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 Die Beziehung zwischen diesen beiden Deklaration ist, dass die `x:`-Präfix-Zuordnung die in der XAML-Sprache definierten Basiselemente auszeichnet, während [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Implementierung ist, die XAML als Sprache nutzt und ein Vokabular seiner eigenen Objekte für XAML definiert. Da die Verwendung von WPF-Vokabular weitaus häufiger als die Verwendung von XAML-Interna sein wird, wird das WPF-Vokabular als Standard zugeordnet.  
  
 Nach der `x:`-Präfix-Konvention für die Zuordnung der Unterstützung für die systeminternen Funktionen der XAML-Sprache folgen Projektvorlagen, Beispielcode und die Dokumentation der Sprachfeatures in diesem [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]. Der XAML-Namespace definiert viele häufig verwendete Funktionen, die auch für einfache WPF-Anwendung erforderlich sind. Um beispielsweise CodeBehind mittels einer partiellen Klasse zu einer XAML-Datei hinzuzufügen, müssen Sie diese Klasse als `x:Class`-Attribut im Stammelement der relevanten XAML-Datei benennen. Genauer: Sie müssen für jedes in einer XAML-Seite definierte Element, auf das Sie als mit einem Schlüssel versehene Ressource zugreifen möchten, ein entsprechendes `x:Key`-Attribut setzen. Weitere Informationen zu diesen und anderen Aspekten von XAML finden Sie unter [Übersicht über XAML (WPF)](xaml-overview-wpf.md) oder [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md).  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>   
## <a name="mapping-to-custom-classes-and-assemblies"></a>Zuordnen von Benutzerdefinierten Klassen und Assemblys  
 Sie können XML-Namespaces bestimmten Assemblys mittels einer Reihe von Token mit `xmlns`-Präfixdeklaration zuordnen, ähnlich wie die standardmäßigen WPF- und XAML-Interna Präfixen im XAML-Namespace zugeordnet sind.  
  
 Die Syntax akzeptiert die folgenden möglichen benannten Token und die folgenden Werte:  
  
 `clr-namespace:` Der CLR-Namespace deklariert innerhalb der Assembly, die als Elemente verfügbar gemachten öffentlichen Typen enthält.  
  
 `assembly=` Die Assembly, die einige oder alle der auf das verwiesen wird, enthält [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Namespace. Dieser Wert ist in der Regel nur der Name der Assembly, nicht der Pfad zu ihr, und er schließt nicht die Erweiterung (z.B. .dll oder .exe) ein. Der Pfad zu dieser Assembly muss als Projektreferenz in der Projektdatei hergestellt werden, die das zuzuordnende XAML enthält. Um Versionierung und Signierung mit starkem Namen, integrieren den `assembly` Wert kann eine Zeichenfolge gemäß <xref:System.Reflection.AssemblyName>, anstatt den einfachen Namen.  
  
 Beachten Sie, dass als Trennzeichen zwischen `clr-namespace`-Token und dessen Wert ein Doppelpunkt (:) verwendet wird, während der `assembly`-Token von seinem Wert mit einem Gleichheitszeichen (=) getrennt ist. Das zwischen diesen beiden Token zu verwendende Zeichen ist ein Semikolon. Darüber hinaus enthalten Sie keine Leerstellen an einer beliebigen Stelle in der Deklaration.  
  
### <a name="a-basic-custom-mapping-example"></a>Ein Beispiel für einfache benutzerdefinierte Zuordnung  
 Der folgende Code definiert eine benutzerdefinierte Beispielklasse:  
  
```csharp  
namespace SDKSample {  
    public class ExampleClass : ContentControl {  
        public ExampleClass() {  
        ...  
        }  
    }  
}  
```  
  
```vb  
Namespace SDKSample  
    Public Class ExampleClass  
        Inherits ContentControl  
         ...  
        Public Sub New()  
        End Sub  
    End Class  
End Namespace  
```  
  
 Diese benutzerdefinierte Klasse wird dann in eine Bibliothek kompiliert, die gemäß den (nicht dargestellten) Projekteinstellungen `SDKSampleLibrary` heißt.  
  
 Um auf diese benutzerdefinierte Klasse zu verweisen, müssen Sie diese auch als Verweis für das aktuelle Projekt hinzufügen. Dazu nutzen Sie in der Regel die Projektmappen-Explorer-Benutzeroberfläche in Visual Studio.  
  
 Nun, da Sie eine Bibliothek mit einer Klasse und einen Verweis darauf in den Projekteinstellungen haben, können Sie die folgende Präfix-Zuordnung als Teil des XAML-Stammelements hinzufügen:  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 Zusammenfassend sehen Sie im Folgenden den XAML-Code mit der benutzerdefinierten Zuordnung, zusammen mit den herkömmlichen Zuordnungen und den x:-Zuordnungen im Stammelement, der dann einen Verweis mittels Präfix verwendet, um `ExampleClass` in der Benutzeroberfläche zu instanziieren:  
  
```xaml  
<Page x:Class="WPFApplication1.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"   
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary">  
  ...  
  <custom:ExampleClass/>  
...  
</Page>  
```  
  
### <a name="mapping-to-current-assemblies"></a>Zuordnen von aktuellen Assemblys  
 `assembly` kann ausgelassen werden, wenn die `clr-namespace` auf die verwiesen wird in der gleichen Assembly wie der Anwendungscode, die die benutzerdefinierten Klassen verweist definiert wird. Eine alternative Syntax für diesen Fall ist die Angabe `assembly=`, ohne Zeichenfolgetoken nach dem Gleichheitszeichen.  
  
 Benutzerdefinierte Klassen können nicht als Stammelement einer Seite verwendet werden, wenn sie in der gleichen Assembly definiert sind. Partielle Klassen müssen nicht zugeordnet werden. Es müssen nur Klassen zugeordnet werden, die keine partielle Klasse einer Seite in Ihrer Anwendung sind, wenn Sie auf diese als Elemente in XAML verweisen möchten.  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>   
## <a name="mapping-clr-namespaces-to-xml-namespaces-in-an-assembly"></a>Zuordnen von CLR-Namespaces zu XML-Namespaces in einer Assembly  
 WPF definiert ein CLR-Attribut, das von XAML-Prozessoren verwendet wird, um mehrere CLR-Namespaces einem einzigen XAML-Namespace zuzuordnen. Dieses Attribut <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, befindet sich auf der Assemblyebene im Quellcode, der die Assembly erzeugt. Der Quellcode der WPF-Assembly verwendet dieses Attribut, um die verschiedenen allgemeinen Namespaces wie z. B. zuzuordnen <xref:System.Windows> und <xref:System.Windows.Controls>, zu der [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] Namespace.  
  
 Die <xref:System.Windows.Markup.XmlnsDefinitionAttribute> akzeptiert zwei Parameter: den Namen der XML/XAML-Namespace und Name des CLR-Namespaces. Mehr als eine <xref:System.Windows.Markup.XmlnsDefinitionAttribute> kann vorhanden sein, um mehrere CLR-Namespaces demselben XML-Namespace zuzuordnen. Sind diese einmal zugeordnet, kann in der CodeBehind-Seite der partiellen Klasse auf Mitglieder dieser Namespaces auf Wunsch auch ohne vollqualifizierten Bezeichner durch Angabe des entsprechenden `using`-Statements verwiesen werden. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.  
  
## <a name="designer-namespaces-and-other-prefixes-from-xaml-templates"></a>Designer-Namespaces und andere Präfixe aus XAML-Vorlagen  
 Wenn Sie mit Entwicklungsumgebungen und/oder Entwurfstools für WPF-XAML arbeiten, werden Sie bemerken, dass es im XAML-Markup weitere definierte XAML-Namespaces/Präfixe gibt.  
  
 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] verwendet einen Designer-Namespace, der in der Regel das Präfix zugeordnet ist `d:`. Neuere Projektvorlagen für WPF ordnen dieses Präfix möglicherweise bereits im Vorfeld zu, um den Austausch von XAML zwischen [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] und andere Entwurfsumgebungen zu unterstützen. Dieser XAML-Designer-Namespace wird verwendet, um bei Roundtrips von XAML-basierten Benutzeroberflächen den jeweiligen Stand des Designs festzuhalten. Er wird ebenfalls für Funktionen wie z.B. `d:IsDataSource` verwendet, die die Laufzeit-Datenquellen in einem Designer aktivieren.  
  
 Ein anderes Präfix, dessen Zuordnung Sie möglicherweise sehen können, ist `mc:`. `mc:` ist für die Markupkompatibilität und nutzt ein Markup-Compatibility-Muster, das nicht unbedingt XAML-spezifischen ist. In gewissem Umfang können die Markupkompatibilitäts-Funktionen verwendet werden, um XAML zwischen Frameworks oder grenzübergreifend mit unterstützenden Implementierungen auszutauschen, zwischen verschiedenen XAML-Schema-Kontexten zu arbeiten, Kompatibilität für eingeschränkte Modi in Designern bereitzustellen, und so weiter. Weitere Informationen zu Markupkompatibilitätskonzepten und deren Beziehung zu WPF, finden Sie unter [Markupkompatibilität (Mc:) Sprachfunktionen](markup-compatibility-mc-language-features.md).  
  
## <a name="wpf-and-assembly-loading"></a>WPF und Laden von Assemblys  
 Der XAML-Schemakontext für WPF-Integration mit dem WPF-Anwendungsmodell, die wiederum die CLR definierte Konzept von <xref:System.AppDomain>. Die folgende Sequenz beschreibt, wie XAML-Schemakontext interpretiert, wie Assemblys geladen werden oder finden von Typen zur Laufzeit oder Entwurfszeit basierend auf der WPF-Verwendung von <xref:System.AppDomain> und anderen Faktoren.  
  
1.  Durchlaufen der <xref:System.AppDomain>, Suchen nach einer bereits geladenen Assembly mit allen Aspekten des Namens, des zuletzt geladenen Assembly wird gestartet.  
  
2.  Wenn der Name qualifiziert ist, rufen Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> für den qualifizierten Namen.  
  
3.  Wenn der Kurzname und das öffentliche Schlüsseltoken eines qualifizierten Namens mit der Assembly übereinstimmen, aus der das Markup geladen wurde, gib diese Assembly zurück.  
  
4.  Verwenden Sie zum Aufrufen der Kurzname und das Token des öffentlichen Schlüssels <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
5.  Wenn der Name nicht qualifiziert ist, rufen Sie <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
 Loose XAML verwendet Schritt 3 nicht, da es nicht aus Assemblys geladen wird.  
  
 Kompilierte XAML für WPF (mithilfe XamlBuildTask generiert) verwendet nicht die bereits geladenen Assemblys aus <xref:System.AppDomain> (Schritt 1). Darüber hinaus sollte der aus XamlBuildTask resultierende Name nie unqualifiziert sein, weshalb Schritt 5 hier nicht anwendbar ist.  
  
 Kompiliertes BAML (mit PresentationBuildTask generiert) verwendet alle Schritte, obwohl auch BAML keine unqualifizierten Assemblynamen enthalten sollte.  
  
## <a name="see-also"></a>Siehe auch

- [Grundlegendes zu XML-Namespaces](https://go.microsoft.com/fwlink/?LinkId=98069)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
