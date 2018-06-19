---
title: 与 SharePoint 使用 SAP 适配器时的注意事项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d310741-b648-4028-a75f-35b843edcc8d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07aef41626c9ac2336565cdca9fa3470bf0144e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218125"
---
# <a name="considerations-when-using-the-sap-adapter-with-sharepoint"></a>与 SharePoint 使用 SAP 适配器时的注意事项
本主题包含有关的问题的信息时使用可能会遇到[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]与 Microsoft Office SharePoint Server，以及解决方法。 问题分为两个类别：  
  
-   一般问题  
  
-   涉及自定义 Web 部件的问题  
  
## <a name="general-issues"></a>一般问题  
 本部分包含没有解决方法，或需要修改的分辨率的应用程序定义文件的问题。  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a>问题 1： 不显示返回的 WCF 服务的简单类型数据  
 **说明**: Microsoft Office SharePoint Server 需要要进行的数据集或集合类型的 WCF 服务返回的数据。 如果 WCF 服务返回的数据的简单类型，Microsoft Office SharePoint Server 将不显示数据。  
  
 **解析**： 没有解决方法。 它是一个与 Microsoft Office SharePoint Server 的已知的限制。  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a>问题 2： 一条错误消息显示如果 WCF 服务返回的数据为 NULL  
 **说明**： 如果 WCF 服务返回的数据为 NULL 值，Microsoft Office SharePoint Server 将显示一条错误消息。 例如，假设你正在使用业务数据列表 Web 部件**Finder**方法实例，并正在寻求 SAP 系统基于搜索表达式中的客户。 你指定的搜索表达式提取一个 NULL 值。 在这种情况下，Microsoft Office SharePoint Server 将显示一条错误消息。  
  
 **解析**： 没有解决方法。 它是一个与 Microsoft Office SharePoint Server 的已知的限制。  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a>问题 3: WCF 服务返回的简单类型的数组不显示  
 **说明**： 如果 WCF 服务返回的数据是简单类型的数组，Microsoft Office SharePoint Server 将不显示数据。 此外，在业务数据目录定义编辑器中返回数组的简单类型执行的方法实例时，会显示以下错误消息:"后端系统适配器返回一个结构使用的相应的元数据 （不兼容实例，但、 参数或 TypeDescriptor）。"  
  
 **解析**： 没有解决方法。 它是使用 Microsoft Office SharePoint Server 和业务数据目录定义编辑器已知的限制。  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a>问题 4： 无法导入一个包含具有大于 300 个字段的复杂类型形参的应用程序定义文件  
 **说明**: Microsoft Office SharePoint Server 无法导入具有 WCF 服务返回的复杂类型参数中的大于 300 个字段并显示一条错误消息，如果你尝试执行此操作的应用程序定义文件。 这是因为 Microsoft Office SharePoint Server 无法显示大于 300 个字段的复杂类型参数的限制。  
  
 **解析**： 使用业务数据目录定义编辑器来限制小于或等于 300 的复杂类型参数的字段数。 具体取决于你的需求，你可以删除复杂类型参数在业务数据目录定义编辑器中，不需要 Microsoft Office SharePoint Server 中显示的字段。  或者，你可以在其中还将应用程序定义文件从业务数据目录定义编辑器导出了所有字段，，然后修改在记事本或任何 XML 创作应用程序以删除不是字段中的应用程序定义文件需要限制和 300 之间的字段数。  
  
##  <a name="Custom_Web_Part"></a>涉及自定义 Web 部件的问题  
 本部分包含有关解决方法需要自定义 Web 部件使用的问题。 有关使用自定义 Web 部件以解决在使用时可能出现的问题的详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和 Microsoft Office SharePoint Server，请参阅[自定义 Web 部件使用的 SAP 适配器](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)。  
  
###  <a name="Issue1"></a>问题 1： 基于多个值的限制与 Microsoft Office SharePoint Server 中显示一条记录  
 **说明**： 如果你想要基于从 SAP 系统的多个值 （输入参数） 的 Microsoft Office SharePoint Server 中显示一条记录，则无法使用任何三个 Web 部件 （业务数据列表、 业务数据项和业务数据相关的列表） 中指定[步骤 3： 创建一个 SharePoint 应用程序检索数据从 SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)中[教程 1： 从 SharePoint 站点上的 SAP 系统提供数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)。  
  
 **解析**： 你必须使用自定义 Web 部件执行此操作。 有关使用自定义 Web 部件的信息，请参阅[自定义 Web 部件使用的 SAP 适配器](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)。 在"步骤 1:: 创建自定义 Web 部件"该主题的你可以在步骤 5 中使用下面的代码示例。 下面的代码示例采用 BankCountry 和 BankKey 作为输入参数，然后将其显示为 Microsoft Office SharePoint Server 中的单个记录。  
  
```  
namespace CustomWebPart  
{  
    public class CustomWebPart : WebPart  
    {  
        private string displayText = "Hello World!";  
  
        [WebBrowsable(true), Personalizable(true)]  
        public string DisplayText  
        {  
            get { return displayText; }  
            set { displayText = value; }  
        }  
        protected override void Render(System.Web.UI.HtmlTextWriter writer)  
        {  
            string BankCountry = "US";  
            string BankKey = "134329042";  
  
/***Step 1: Get the required entity and method.***/  
  
            LobSystem newSystem = ApplicationRegistry.GetLobSystems()["BAPI_BANK_GETDETAIL"]; // Name specified in application definition file  
            LobSystemInstance newSystemInstance = newSystem.GetLobSystemInstances()["BAPI_BANK_GETDETAIL_Instance"]; // Name specified in application definition file  
            Entity CategoryEntity = newSystem.GetEntities()["Entity"]; // Name specified in application definition file  
            Method newMethod = CategoryEntity.GetMethods()["BAPI_BANK_GETDETAIL"]; // Name specified in application definition file  
            MethodInstance methodInstance = newMethod.GetMethodInstances()["MethodInstance"]; // Name specified in application definition file  
  
/***Step 2: Get the list of input parameters.***/  
  
            Object[] args = methodInstance.GetMethod().CreateDefaultParameterInstances(methodInstance); //Get the default values of the input parameters.  
            Object[] ArgsInput = new Object[args.Length];  
  
/***Step 3: Assign them required values.***/  
  
            Type t = null;  
            char[] myString = BankCountry.ToCharArray();  
            String s = new String(myString);  
            t = s.GetType();  
            ArgsInput[0] = Activator.CreateInstance(t, myString);  
  
            myString = BankKey.ToCharArray();  
            s = new String(myString);  
            t = s.GetType();  
            ArgsInput[1] = Activator.CreateInstance(t, myString);  
  
/***Step 4: Execute the particular method instance using the required value.***/  
  
            IEntityInstance IE = (IEntityInstance)CategoryEntity.Execute(methodInstance, newSystemInstance, ref ArgsInput); //Method instance of type Specific Finder is being used here.  
  
/***Step 5: Display the output on the custom Web Part in Microsoft Office SharePoint Server.***/  
  
            writer.Write("<table>");  
            writer.Write("<tr>");  
            foreach (Field f in CategoryEntity.GetFinderView().Fields)  
            {  
                writer.Write("<td>");  
                writer.Write(IE[f]);  
                writer.Write("</td>");  
            }  
            writer.Write("</tr>");  
            writer.Write("</table>");  
        }  
    }  
  
```  
  
> [!NOTE]
>  应用程序定义文件必须包含**特定的 Finder**方法实例。 A**特定的 Finder**方法找到了一个基于标识符的特定记录。 有关创建信息**特定的 Finder**方法实例时，请参阅中的"要求 2:: 检索详细信息的特定客户从列表的客户"[步骤 2： 为 SAP 创建应用程序定义文件项目](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)中[教程 1： 从 SharePoint 站点上的 SAP 系统提供数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)。  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a>问题 2： 不能指定对数组元素的值  
 **说明**: WCF 服务的输入的参数是一个数组，如果你不能指定到使用在创建使用业务数据目录定义编辑器的应用程序定义文件中定义的筛选器的数组元素的值。 这意味着，你不能用于业务数据列表或业务数据项 Web 部件在 Microsoft Office SharePoint Server 中指定这些到 WCF 服务的输入参数 （数组的元素） 的值。 这是由于应用程序定义文件中定义数组的方法。  
  
 **解析**： 使用自定义 Web 部件将值分配到数组元素。 有关使用自定义 Web 部件的信息，请参阅[自定义 Web 部件使用的 SAP 适配器](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)。 例如，可以使用下面的代码示例中的步骤 3 中"问题 1： 在 Microsoft Office SharePoint Server 中显示的单个记录限制基于多个值"将值分配到数组元素。  
  
```  
/***Assign required values to parameters of type array.***/   
/***Assumption is that the ith parameter of Method is of type Array and all the simple type elements in the array are of string type.***/  
  
            Type t = asm.GetType(args[i].GetType().ToString()); // Get type of the parameter  
            Type TElement = t.GetElementType(); // Getting type of element of array  
            int index = 5; //Size of Array  
            Array ElementArray = Array.CreateInstance(TElement, index); //Creating an array of length: index  
  
            for (int ind = 0; ind < index; ind++)  
            {  
                //Creating an instance of an element of array  
                object ElementType = Activator.CreateInstance(TElement);  
                FieldInfo[] FI = ElementType.GetType().GetFields();  
                for (int f = 0; f \< FI.Length; f++)  
                {  
                    ElementType.GetType().GetFields()[f].SetValue(ElementType, (Object)"ElementValue");  
                }  
                ElementArray.SetValue(ElementType, ind);  
            }  
  
            ArgsInput[i] = (object)ElementArray; // As shown in sample, ArgsInput is fed as input while executing Method Instance  
  
```  
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a>指定给复杂类型参数的 NULL 值的问题 3： 限制  
 **说明**： 如果 Microsoft Office SharePoint Server 中不指定任何值为复杂类型参数从 Web 部件，NULL 应传递为复杂类型参数的值到 WCF 服务。 但是，非 NULL 值传递为复杂类型参数，并且为其子元素 （的简单类型） 传递了 NULL。 这将导致预期的消息架构与传递到 WCF 服务的消息架构不匹配。 因此，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可能会显示一条错误消息。  
  
> [!NOTE]
>  若要了解复杂类型参数的默认值，当从 Microsoft Office SharePoint Server 中的 Web 部件不传递任何值，请使用步骤 2 中的代码示例中所述"问题 1： 使用 Microsoft Office SharePoint Server 中显示一条记录的限制基于多个值。"  
  
 **解析**： 使用自定义 Web 部件将 NULL 值分配给复杂类型参数。 有关使用自定义 Web 部件的信息，请参阅[自定义 Web 部件使用的 SAP 适配器](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
[使用带有 SharePoint SAP 适配器](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)