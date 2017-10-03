---
title: "步骤 6： 为 Echo 适配器实现的元数据解析处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0105d1b0-efbd-457b-af0d-08e29408a318
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 022da31cacedaa59c9e5821fb049165f463c7f06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter"></a>步骤 6： 为 Echo 适配器实现的元数据解析处理程序
![步骤 6 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")  
  
 **完成时间：** 45 分钟  
  
 在此步骤中，你实现`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`界面，用于解决操作和类型为 echo 适配器的元数据。 无论您的适配器的功能，则必须实现此接口。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成为您调用 EchoAdapterMetadataResolverHandler 派生的类。  
  
 在以下部分中，你将更新 EchoAdapterMetadataResolverHandler 类，以获取更好地了解如何实现此接口。 完成此步骤后，必须解决 echo 适配器处理程序的工作元数据。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，你必须已成功完成[步骤 5： 为 Echo 适配器实现的元数据搜索处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)。 您还必须了解以下操作和类型类：  
  
-   `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationParameter`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationResult`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMember`  
  
-   `Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`  
  
-   `Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`  
  
## <a name="the-imetadataresolverhandler-interface"></a>IMetadataResolverHandler 接口  
  
```  
public interface IMetadataResolverHandler : IConnectionHandler, IDisposable  
  {  
      bool IsOperationMetadataValid(string operationId, DateTime lastUpdatedTimestamp, TimeSpan timeout);        
      bool IsTypeMetadataValid(string typeId, DateTime lastUpdatedTimestamp, TimeSpan timeout);  
      OperationMetadata ResolveOperationMetadata(string operationId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
      TypeMetadata ResolveTypeMetadata(string typeId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
  }  
```  
  
 下表描述每种方法执行的操作：  
  
|**方法名称**|**Description**|  
|---------------------|---------------------|  
|IsOperationMetadataValid|如果自指定日期和时间以来未更改的类型元数据，则返回 true|  
|IsTypeMetadataValid|返回一个布尔值，该值指示指定的类型元数据是否有效。|  
|ResolveOperationMetadata|解析为相应的操作 ID`Microsoft.ServiceModel.Channels.Common.OperationMetadata`|  
|ResolveTypeMetadata|解析为相应的提供的元数据 typeId `Microsoft.ServiceModel.Channels.Common.TypeMetadata`。|  
  
### <a name="to-implement-the-isoperationmetadatavalid-method"></a>若要实现 IsOperationMetadataValid 方法  
  
1.  在解决方案资源管理器中，双击**EchoAdapterMetadataResolverHandler.cs**文件。  
  
2.  在 Visual Studio 编辑器中，右键单击任意位置在编辑器中，在上下文菜单中，依次指向**大纲**，然后单击**停止大纲显示**。  
  
3.  在 Visual Studio 编辑器中，查找**IsOperationMetadataValid**方法，在此方法中，将现有与下面的单个语句以指示每个指定的操作元数据是否有效。  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-istypemetadatavalid-method"></a>若要实现 IsTypeMetadataValid 方法  
  
-   在 Visual Studio 编辑器中，查找**IsTypeMetadataValid**方法，在此方法中，将现有与下面的单个语句以指示每个指定的类型元数据是否有效。  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-resolveoperationmetadata-method"></a>若要实现 ResolveOperationMetadata 方法  
  
1.  在 Visual Studio 编辑器中，查找**ResolveOperationMetadata**方法，在此方法中，将现有替换为以下若要解决此 OnReceiveEcho 操作，void OnReceiveEcho （长 fileLength Uri 路径)。  
  
    ```csharp  
    extraTypeMetadataResolved = null;  
    switch( operationId )  
    {  
        case "Echo/OnReceiveEcho":  
            ParameterizedOperationMetadata om = new ParameterizedOperationMetadata(operationId, "OnReceiveEcho");  
            om.OriginalName = "lobNotification";  
            om.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
            om.OperationGroup = "EchoInboundContract";  
            om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
            // syntax: void OnReceiveEcho(Uri path, long fileLength)  
            OperationParameter parmPath = new OperationParameter("path", OperationParameterDirection.In, QualifiedType.UriType, false);  
            parmPath.Description = "Absolute path of the file";  
            OperationParameter parmLength = new OperationParameter("length", OperationParameterDirection.In, QualifiedType.LongType, false);  
            parmLength.Description = "Length of the file received in this location.";  
            om.Parameters.Add(parmPath);  
            om.Parameters.Add(parmLength);  
            om.OperationResult = OperationResult.Empty;  
            return om;  
    ```  
  
2.  继续添加以下方法解决 Echo/EchoStrings 操作，字符串 [] EchoStrings(string data)。  
  
    ```csharp  
    case "Echo/EchoStrings":  
        om = new ParameterizedOperationMetadata(operationId, "EchoStrings");  
        om.OriginalName = "lobEchoStrings";  
        om.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
        om.OperationGroup = "EchoOutboundContract";  
        om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
        // syntax: string[] EchoStrings(string data)  
        OperationParameter parmData = new OperationParameter("data", OperationParameterDirection.In, QualifiedType.StringType, false);  
        parmData.Description = "Input string";  
        om.Parameters.Add(parmData);  
        om.OperationResult = new OperationResult(QualifiedType.StringType, true);  
        return om;  
    ```  
  
3.  继续添加以下逻辑，若要解决此 Echo/EchoStrings 操作，字符串 [] EchoStrings(string data)。  
  
    ```csharp  
    case "Echo/EchoGreetings":  
        om = new ParameterizedOperationMetadata(operationId, "EchoGreetings");  
        om.OriginalName = "lobEchoGreetings";  
        om.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
        om.OperationGroup = "EchoOutboundContract";  
        om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
        // syntax: Greeting[] EchoGreetings(Greeting greeting)  
        ComplexQualifiedType cqtGreeting = new ComplexQualifiedType("Types/GreetingType");  
        OperationParameter parmGreeting = new OperationParameter("greeting", OperationParameterDirection.In, cqtGreeting, false);  
        parmGreeting.Description = "Input greeting";  
        om.Parameters.Add(parmGreeting);  
        om.OperationResult = new OperationResult(cqtGreeting, true);  
        return om;  
    ```  
  
4.  继续添加以下逻辑，若要解决 CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath) 操作。  
  
    ```csharp  
    case "Echo/EchoCustomGreetingFromFile":  
        om = new ParameterizedOperationMetadata(operationId, "EchoCustomGreetingFromFile");  
        om.OriginalName = "lobEchoGreetingUsePredefinedMetadata";  
        om.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.  The Greeting type metadata is created using predefined XSD file.";  
        om.OperationGroup = "EchoOutboundContract";  
        om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
        OperationParameter parmGreetingInstancePath = new OperationParameter("greetingInstancePath", OperationParameterDirection.In, QualifiedType.UriType, false);  
        om.Parameters.Add(parmGreetingInstancePath);  
        ComplexQualifiedType cqtGreetingXsd = new ComplexQualifiedType("Types/CustomGreetingFromXsdType");  
        om.OperationResult = new OperationResult(cqtGreetingXsd, false);  
  
        // resolve extra typemetadata here  
        extraTypeMetadataResolved = new TypeMetadataCollection();  
  
        // use a predefined schema to generate metadata for this type  
        CustomGreetingTypeMetadata tmGreetingXsd = new CustomGreetingTypeMetadata("Types/CustomGreetingFromXsdType", "CustomGreeting");  
        extraTypeMetadataResolved.Add(tmGreetingXsd);                   
        return om;  
  
    ```  
  
5.  继续添加以下内容以处理默认情况。  
  
    ```csharp  
        default:  
            throw new AdapterException("Cannot resolve metadata for operation identifier " + operationId);  
    }  
    ```  
  
### <a name="to-implement-the-resolvetypemetadata-method"></a>若要实现 ResolveTypeMetadata 方法  
  
-   在 Visual Studio 编辑器中，查找**ResolveTypeMetadata**方法，在此方法中，将替换为以下返回现有`Microsoft.ServiceModel.Channels.Common.TypeMetadata`对象。  
  
    ```csharp  
    extraTypeMetadataResolved = null;  
    string typeNamespaceForGreeting = EchoAdapter.SERVICENAMESPACE + "/Types";  
    switch (typeId)  
    {  
        case "Types/GreetingType":  
            StructuredTypeMetadata tmGreeting = new StructuredTypeMetadata(typeId, "Greeting");  
            tmGreeting.TypeNamespace = typeNamespaceForGreeting;  
            tmGreeting.Members.Add(new TypeMember("id", QualifiedType.GuidType, false));  
            tmGreeting.Members.Add(new TypeMember("sentDateTime", QualifiedType.DateTimeType, false));  
            ComplexQualifiedType cqtName = new ComplexQualifiedType("Types/NameType");  
            tmGreeting.Members.Add(new TypeMember("name", cqtName, false));  
            tmGreeting.Members.Add(new TypeMember("greetingText", QualifiedType.StringType, false));  
            return tmGreeting;  
  
        case "Types/NameType":  
            StructuredTypeMetadata tmName = new StructuredTypeMetadata(typeId, "Name");  
            tmName.TypeNamespace = typeNamespaceForGreeting;  
            ComplexQualifiedType cqtSalutation = new ComplexQualifiedType("Types/SalutationType");  
            tmName.Members.Add(new TypeMember("salutation", cqtSalutation, false));  
            tmName.Members.Add(new TypeMember("firstName", QualifiedType.StringType, false));  
            tmName.Members.Add(new TypeMember("middleName", QualifiedType.StringType, false));  
            tmName.Members.Add(new TypeMember("lastName", QualifiedType.StringType, false));  
            return tmName;  
  
        case "Types/SalutationType":  
            EnumTypeMetadata tmSalutation = new EnumTypeMetadata(typeId, "Salutation", new string[] { "Mr.", "Mrs.", "Dr.", "Ms.", "Miss" });  
            tmSalutation.TypeNamespace = typeNamespaceForGreeting;  
            return tmSalutation;  
  
        default:  
            throw new AdapterException("Cannot resolve metadata for type identifier " + typeId);  
    }  
  
    ```  
  
### <a name="to-define-the-custom-greeting-type-metadata-class"></a>若要定义自定义问候语类型元数据类  
  
1.  在解决方案资源管理器，右键单击**Echo 适配器**项目，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项**对话框中，在**模板**，单击**类**。  
  
3.  在**名称**文本框中，键入**CustomGreetingTypeMetadata**。  
  
4.  单击 **“添加”**。  
  
5.  在 Visual Studio 编辑器中，替换为以下替换现有代码：  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using Microsoft.ServiceModel.Channels.Common;  
    using System.Xml;  
    using System.Xml.Schema;  
    using System.IO;  
  
    namespace Microsoft.Adapters.Samples.EchoV2  
    {  
        public class CustomGreetingTypeMetadata : TypeMetadata  
        {  
            private const string CONST_METADATA_FILE_NAME = "Microsoft.Adapters.Samples.EchoV2.CustomGreeting.xsd";  
  
            public CustomGreetingTypeMetadata(string typeId, string typeName)  
                : base(typeId, typeName)  
            {  
                this.TypeNamespace = EchoAdapter.SERVICENAMESPACE + "/PreDefinedTypes";  
                this.Description = " ";  
                this.CanUseCommonCache = true;  
                // if the nillable is not set to true, the generated proxy wraps the operation  
                // with request and response objects  
                this.IsNillable = true;  
            }  
  
            /// <summary>  
            /// Override the base ExportXmlSchema to provide own   
            /// custom XML Schema  
            /// </summary>  
            /// <param name="schemaExportContext"></param>  
            /// <param name="metadataLookup"></param>  
            /// <param name="timeout"></param>  
            public override void ExportXmlSchema(XmlSchemaExportContext schemaExportContext, MetadataLookup metadataLookup, TimeSpan timeout)  
            {  
                if (schemaExportContext == null)  
                {  
                    throw new AdapterException("Schema export context is null.");  
                }  
                // Read in XML Schema file or create XmlSchema object yourself  
                Stream predefinedXsdFile = System.Reflection.Assembly.GetExecutingAssembly().GetManifestResourceStream(CONST_METADATA_FILE_NAME);  
                XmlReader reader = XmlReader.Create(predefinedXsdFile);  
                XmlSchema schema = XmlSchema.Read(reader, null);  
                if (!IsComplexTypeAlreadyDefined(schemaExportContext.SchemaSet, schema))  
                {  
                    schemaExportContext.SchemaSet.Add(schema);  
                    if (!schemaExportContext.NamespacePrefixSet.ContainsKey(this.TypeNamespace))  
                    {  
                        schemaExportContext.NamespacePrefixSet.Add(this.TypeNamespace, getUniqueNamespacePrefix(schemaExportContext, 0));  
                    }  
                }  
                reader.Close();  
            }  
  
            /// <summary>  
            /// A default value cannot be set for this type metadata.  
            /// </summary>  
            public override bool CanSetDefaultValue  
            {  
                get { return false; }  
            }  
  
            /// <summary>  
            /// Helper function to see if the schema is already defined in the   
            /// XmlSchemaSet.  
            /// </summary>  
            /// <param name="oldschemaset"></param>  
            /// <param name="newschema"></param>  
            /// <returns></returns>  
            public static bool IsComplexTypeAlreadyDefined(XmlSchemaSet oldschemaset, XmlSchema newschema)  
            {  
                // ensure correct namespace was defined in the passed-in schema  
                foreach (XmlSchema schema in oldschemaset.Schemas(newschema.TargetNamespace))  
                {  
                    foreach (XmlSchemaObject newschemaObject in newschema.Items)  
                    {  
                        if (newschemaObject is XmlSchemaComplexType)  
                        {  
                            //check for the definition of complex type in the schemaset             
                            foreach (XmlSchemaObject schemaObject in schema.Items)  
                            {  
                                XmlSchemaComplexType complexType = schemaObject as XmlSchemaComplexType;  
                                // Definition of this Complex Type already exists  
                                if (complexType != null && String.Compare(complexType.Name, ((XmlSchemaComplexType)newschemaObject).Name, false, System.Globalization.CultureInfo.InvariantCulture) == 0)  
                                    return true;  
                            }  
                        }  
                    }  
                }  
                return false;  
            }  
  
            /// <summary>  
            /// Helper function to generate a unique namespace prefix  
            /// </summary>  
            /// <param name="schemaExportContext"></param>  
            /// <param name="startSuffix"></param>  
            /// <returns></returns>  
            private string getUniqueNamespacePrefix(XmlSchemaExportContext schemaExportContext, int startSuffix)  
            {  
                string defaultPrefix = "ns";  
                string val = defaultPrefix + startSuffix;  
                if (schemaExportContext.NamespacePrefixSet.ContainsValue(val))  
                {  
                    return getUniqueNamespacePrefix(schemaExportContext, ++startSuffix);  
                }  
                else  
                {  
                    return val;  
                }  
            }  
        }  
    }  
    ```  
  
6.  在 Visual Studio 中，从**文件**菜单上，单击**保存所有**。  
  
### <a name="to-create-the-custom-greeting-xml-schema-definition"></a>若要创建自定义问候语 XML 架构定义  
  
1.  在解决方案资源管理器，右键单击**Echo 适配器**项目，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项**对话框中，在**模板**，单击**XML 架构**。  
  
3.  在**名称**文本框中，键入**CustomGreeting**。  
  
4.  单击 **“添加”**。  
  
5.  在解决方案资源管理器，右键单击**CustomGreeting.xsd**文件，然后选择**查看代码**。  
  
6.  在 Visual Studio 编辑器中，开始通过将现有代码替换为以下代码，以开始 CustomGreeting 架构定义：  
  
    ```csharp  
    <?xml version="1.0" encoding="utf-8" ?>   
    <xs:schema id="XMLSchema1"   
                      targetNamespace="http://tempuri.org/XMLSchema1.xsd"  
                      elementFormDefault="qualified"  
                      xmlns="http://tempuri.org/XMLSchema1.xsd"  
                      xmlns:mstns="http://tempuri.org/XMLSchema1.xsd"  
                      xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    </xs:schema>  
    ```  
  
     替换为以下代码，开始 CustomGreeting 架构的定义：  
  
    ```csharp  
    <?xml version="1.0" encoding="utf-16"?>  
    <xsd:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" elementFormDefault="qualified" targetNamespace="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" xmlns:xsd ="http://www.w3.org/2001/XMLSchema">  
    ```  
  
7.  添加以下项来定义 CustomGreeting 元素：  
  
    ```csharp  
    <xsd:element name="greeting" type="CustomGreeting" />  
    ```  
  
8.  现在添加 CustomGreeting 复杂类型的定义：  
  
    ```csharp  
    <xsd:complexType name="CustomGreeting">  
      <xsd:sequence>  
        <xsd:element name="address" type="UsAddress" />  
        <xsd:element name="greetingText" type="xsd:string" />  
      </xsd:sequence>  
    </xsd:complexType>  
    ```  
  
9. 通过添加 UsAddress 复杂类型继续 CustomGreeting 架构定义：  
  
    ```csharp  
    <xsd:complexType name="UsAddress">  
      <xsd:sequence>  
        <xsd:element minOccurs="1" maxOccurs="1" name="street1" nillable="true" type="xsd:string" />  
        <xsd:element minOccurs="0" maxOccurs="1" name="street2" type="xsd:string" />  
        <xsd:element minOccurs="1" maxOccurs="1" name="city" type="xsd:string" />  
        <xsd:element minOccurs="1" maxOccurs="1" name="state" type="xsd:string" />  
        <xsd:element name="zip" type="PostalCode" />  
      </xsd:sequence>  
    </xsd:complexType>  
    ```  
  
10. 通过添加 PostalCode 简单类型和架构的结束标记完成 CustomGreeting 架构的定义：  
  
    ```csharp  
      <xsd:simpleType name="PostalCode">  
        <xsd:restriction base="xsd:positiveInteger">  
          <xsd:pattern value="\d{5}" />  
        </xsd:restriction>  
      </xsd:simpleType>  
    </xsd:schema>  
    ```  
  
11. 现在更新此文件的生成操作，因此它将被视为嵌入的资源。 若要这样做，请在 Visual Studio 解决方案窗格中，右键单击该文件，然后选择**属性**。 更改生成操作从**无**到**嵌入资源**。  
  
12. 在 Visual Studio 中，从**文件**菜单上，单击**保存所有**。  
  
> [!NOTE]
>  保存所做的工作。 你可以安全地在此时关闭 Visual Studio 或转到下一步，[步骤 7： 为 Echo 适配器实现同步的出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)。  
  
## <a name="what-did-i-just-do"></a>未我只需做什么？  
 你只需实现解析为 echo 适配器的功能的元数据。  
  
## <a name="next-steps"></a>后续步骤  
 在下一步的步骤中，为 Echo 适配器实现同步的出站处理程序。 您然后实现同步的入站处理程序然后构建和部署和 Echo 适配器。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 5： 为 Echo 适配器实现的元数据搜索处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)   
 [步骤 7： 为 Echo 适配器实现同步的出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)   
 [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)