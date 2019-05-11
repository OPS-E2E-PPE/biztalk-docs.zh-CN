---
title: 与 SharePoint 结合使用 Oracle Business Suite 适配器时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56de6267-ec34-4bd2-abd1-3f2b69876b36
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94dd9bd4f3c80ba76edc2d84fa8757336183802
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375601"
---
# <a name="considerations-using-the-oracle-business-suite-adapter-with-sharepoint"></a>与 SharePoint 结合使用 Oracle Business Suite 适配器时的注意事项
本主题包含有关的问题的信息可能会遇到同时使用[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]使用 Microsoft Office SharePoint Server，以及解决方法。 问题分为两个类别：  
  
-   常规问题  
  
-   涉及自定义 Web 部件的问题  
  
## <a name="general-issues"></a>一般问题  
 本部分包含没有解决方法中的问题。  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a>问题 1:不显示 WCF 服务返回简单类型数据  
 **说明**:Microsoft Office SharePoint Server 需要为数据集或集合类型的 WCF 服务返回的数据。 如果 WCF 服务返回的数据的简单类型，则 Microsoft Office SharePoint Server 不显示数据。  
  
 **解析**:没有解决方法。 这是一个使用 Microsoft Office SharePoint Server 的已知的限制。  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a>问题 2:如果 WCF 服务返回的数据为 NULL，将显示一条错误消息  
 **说明**:如果 WCF 服务返回的数据为 NULL 值，Microsoft Office SharePoint Server 将显示一条错误消息。 例如，假设要使用的业务数据列表 Web 部件**Finder**方法实例，并且要搜索 Oracle E-business Suite 中的客户根据搜索表达式。 指定的搜索表达式中提取一个 NULL 值。 在这种情况下，Microsoft Office SharePoint Server 将显示一条错误消息。  
  
 **解析**:没有解决方法。 这是一个使用 Microsoft Office SharePoint Server 的已知的限制。  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a>问题 3:不显示 WCF 服务返回简单类型的数组  
 **说明**:如果 WCF 服务返回的数据是简单类型的数组，Microsoft Office SharePoint Server 将不显示数据。 此外，在执行方法实例中 Business Data Catalog Definition Editor 返回简单类型的数组时，将显示以下错误消息："后端系统适配器返回结构与相应的元数据 （MethodInstance、 参数或 TypeDescriptor） 不兼容。"  
  
 **解析**:没有解决方法。 它是使用 Microsoft Office SharePoint Server 和 Business Data Catalog Definition Editor 已知的限制。  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a>问题 4:无法导入包含复杂类型参数都有 300 多个字段的应用程序定义文件  
 **说明**:Microsoft Office SharePoint Server 无法导入应用程序定义文件中的 WCF 服务，返回的复杂类型参数的 300 多个字段并显示一条错误消息，如果您尝试执行此操作。 这是因为不能够显示 300 多个字段的复杂类型参数的 Microsoft Office SharePoint Server 的限制。  
  
 **解析**:使用 Business Data Catalog Definition Editor 可限制小于或等于 300 的复杂类型参数的字段的数目。 具体取决于你的要求，可以删除复杂类型参数在 Business Data Catalog Definition Editor 不需要 Microsoft Office SharePoint Server 中显示的字段。  或者，您可以还将应用程序定义文件从 Business Data Catalog Definition Editor 导出所有字段，然后修改在记事本或任何 XML 创作应用程序以删除不是字段中的应用程序定义文件必须以限制为 300 的字段数。  
  
##  <a name="Custom_Web_Part"></a> 涉及自定义 Web 部件的问题  
 本部分包含的自定义 Web 部件使用需要解决的问题。 有关使用自定义 Web 部件以解决可能会使用时产生的问题的详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]和 Microsoft Office SharePoint Server，请参阅[如何使用自定义 web 部件与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)。  
  
###  <a name="Issue1"></a> 问题 1:在 Microsoft Office SharePoint Server 中显示一条记录限制基于多个值  
 **说明**:如果你想要在基于多个值 （输入参数） 从 Oracle E-business Suite 的 Microsoft Office SharePoint Server 中显示一条记录，则无法使用任何三个 Web 部件 （业务数据列表中，业务数据项和业务数据相关列表）步骤 3 中指定：创建 SharePoint 应用程序将数据从 Oracle E-business Suite 中检索[教程：从 SharePoint 站点上的 Oracle E-business Suite 中呈现数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。  
  
 **解析**:必须使用自定义 Web 部件来执行此操作。 有关使用自定义 Web 部件的信息，请参阅[如何使用自定义 web 部件与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)。 在"步骤 1:创建自定义 Web 部件"该主题的则可以在步骤 5 中使用下面的代码示例。 下面的代码示例采用 BankCountry 和 BankKey 作为输入参数，然后显示其作为 Microsoft Office SharePoint Server 中的单个记录。  
  
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
>  应用程序定义文件必须包含**特定的 Finder**方法实例。 一个**特定的 Finder**方法查找基于标识符的特定记录。 有关创建信息**特定的 Finder**方法实例，请参阅"要求 2:检索详细信息的客户列表从特定客户的"在[步骤 2:创建用于 Oracle E-business Suite 项目的应用程序定义文件](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)在[教程：从 SharePoint 站点上的 Oracle E-business Suite 中呈现数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a>问题 2:不能指定为数组元素的值  
 **说明**:如果 WCF 服务的输入的参数是一个数组，则无法指定使用在使用 Business Data Catalog Definition Editor 创建的应用程序定义文件中定义的筛选器的数组元素的值。 这意味着，您不能使用的业务数据列表或业务数据 Web 部件在 Microsoft Office SharePoint Server 中指定这些输入参数 （数组的元素） 的 WCF 服务的值。 这是因为应用程序定义文件中定义数组的方式。  
  
 **解析**:使用自定义 Web 部件将值分配给数组元素。 有关使用自定义 Web 部件的信息，请参阅[如何使用自定义 web 部件与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)。 例如，可以使用下面的代码示例中的步骤 3 中"问题 1:在 Microsoft Office SharePoint Server 中显示一条记录限制基于多个值"将值分配到数组元素。  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a>问题 3:指定到复杂类型参数的 NULL 值的限制  
 **说明**:如果 Microsoft Office SharePoint Server 中不指定 Web 部件中的一个复杂类型参数的任何值，NULL 应传递复杂类型参数的值作为到 WCF 服务。 但是，为复杂类型参数，传递了非 NULL 值和 NULL 传递 （的简单类型） 及其子元素。 这将导致预期的消息架构传递给 WCF 服务的消息架构不匹配。 因此，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可能会显示一条错误消息。  
  
> [!NOTE]
>  若要从 Microsoft Office SharePoint Server 中的 Web 部件不传递任何值时，找出复杂类型参数的默认值，请使用步骤 2 中的代码示例中所述"问题 1:在 Microsoft Office SharePoint Server 中显示一条记录限制基于多个值。"  
  
 **解析**:使用自定义 Web 部件将 NULL 值分配到复杂类型参数。 有关使用自定义 Web 部件的信息，请参阅[如何使用自定义 web 部件与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)。  
  
## <a name="see-also"></a>请参阅  
[使用包含 SharePoint 的 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)