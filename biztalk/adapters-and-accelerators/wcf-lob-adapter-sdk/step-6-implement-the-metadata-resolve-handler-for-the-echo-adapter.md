---
title: 步骤 6：实现 Echo 适配器的元数据解析处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0105d1b0-efbd-457b-af0d-08e29408a318
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98171f958a1e16b5078fb570b107ffcf93cd5954
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363134"
---
# <a name="step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter"></a><span data-ttu-id="5069d-102">步骤 6：实现 Echo 适配器的元数据解析处理程序</span><span class="sxs-lookup"><span data-stu-id="5069d-102">Step 6: Implement the Metadata Resolve Handler for the Echo Adapter</span></span>
<span data-ttu-id="5069d-103">![步骤 6 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span><span class="sxs-lookup"><span data-stu-id="5069d-103">![Step 6 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span></span>  
  
 <span data-ttu-id="5069d-104">**若要完成的时间：** 45 分钟</span><span class="sxs-lookup"><span data-stu-id="5069d-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="5069d-105">在此步骤中，您实现`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`接口解析操作，并键入 echo 适配器的元数据。</span><span class="sxs-lookup"><span data-stu-id="5069d-105">In this step, you implement the `Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler` interface to resolve operation and type metadata for the echo adapter.</span></span> <span data-ttu-id="5069d-106">无论您的适配器的功能，您必须实现此接口。</span><span class="sxs-lookup"><span data-stu-id="5069d-106">Regardless of your adapter's capability, you must implement this interface.</span></span> <span data-ttu-id="5069d-107">[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成派生的类为您调用 EchoAdapterMetadataResolverHandler。</span><span class="sxs-lookup"><span data-stu-id="5069d-107">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the derived class called EchoAdapterMetadataResolverHandler for you.</span></span>  
  
 <span data-ttu-id="5069d-108">在以下部分中，更新 EchoAdapterMetadataResolverHandler 类，以获取更好地了解如何实现此接口。</span><span class="sxs-lookup"><span data-stu-id="5069d-108">In the following section, you update the EchoAdapterMetadataResolverHandler class to get a better understanding on how to implement this interface.</span></span> <span data-ttu-id="5069d-109">完成此步骤，必须解决 echo 适配器处理程序处理元数据。</span><span class="sxs-lookup"><span data-stu-id="5069d-109">When you complete this step, you have a working metadata resolve handler for the echo adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5069d-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="5069d-110">Prerequisites</span></span>  
 <span data-ttu-id="5069d-111">在开始此步骤之前，你必须已成功完成[步骤 5:实现 Echo 适配器的元数据搜索处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5069d-111">Before you begin this step, you must have successfully completed [Step 5: Implement the Metadata Search Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="5069d-112">您还必须了解以下操作和类型类：</span><span class="sxs-lookup"><span data-stu-id="5069d-112">You must also understand the following operation and type classes:</span></span>  
  
-   `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationParameter`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationResult`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMember`  
  
-   `Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`  
  
-   `Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`  
  
## <a name="the-imetadataresolverhandler-interface"></a><span data-ttu-id="5069d-113">IMetadataResolverHandler 接口</span><span class="sxs-lookup"><span data-stu-id="5069d-113">The IMetadataResolverHandler Interface</span></span>  
  
```  
public interface IMetadataResolverHandler : IConnectionHandler, IDisposable  
  {  
      bool IsOperationMetadataValid(string operationId, DateTime lastUpdatedTimestamp, TimeSpan timeout);        
      bool IsTypeMetadataValid(string typeId, DateTime lastUpdatedTimestamp, TimeSpan timeout);  
      OperationMetadata ResolveOperationMetadata(string operationId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
      TypeMetadata ResolveTypeMetadata(string typeId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
  }  
```  
  
 <span data-ttu-id="5069d-114">下表描述每个方法执行的操作：</span><span class="sxs-lookup"><span data-stu-id="5069d-114">The following table describes what each method does:</span></span>  
  
|<span data-ttu-id="5069d-115">**方法名称**</span><span class="sxs-lookup"><span data-stu-id="5069d-115">**Method Name**</span></span>|<span data-ttu-id="5069d-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="5069d-116">**Description**</span></span>|  
|---------------------|---------------------|  
|<span data-ttu-id="5069d-117">IsOperationMetadataValid</span><span class="sxs-lookup"><span data-stu-id="5069d-117">IsOperationMetadataValid</span></span>|<span data-ttu-id="5069d-118">如果自指定日期和时间以来未更改的类型元数据，则返回 true</span><span class="sxs-lookup"><span data-stu-id="5069d-118">Returns a true if the type metadata has not changed since the date and time specified</span></span>|  
|<span data-ttu-id="5069d-119">IsTypeMetadataValid</span><span class="sxs-lookup"><span data-stu-id="5069d-119">IsTypeMetadataValid</span></span>|<span data-ttu-id="5069d-120">返回一个布尔值，该值指示指定的类型元数据是否有效。</span><span class="sxs-lookup"><span data-stu-id="5069d-120">Returns a Boolean value that indicates whether the specified type metadata is valid.</span></span>|  
|<span data-ttu-id="5069d-121">ResolveOperationMetadata</span><span class="sxs-lookup"><span data-stu-id="5069d-121">ResolveOperationMetadata</span></span>|<span data-ttu-id="5069d-122">解析为相应的操作 ID `Microsoft.ServiceModel.Channels.Common.OperationMetadata`</span><span class="sxs-lookup"><span data-stu-id="5069d-122">Resolves an operation ID to corresponding `Microsoft.ServiceModel.Channels.Common.OperationMetadata`</span></span>|  
|<span data-ttu-id="5069d-123">ResolveTypeMetadata</span><span class="sxs-lookup"><span data-stu-id="5069d-123">ResolveTypeMetadata</span></span>|<span data-ttu-id="5069d-124">解析为相应的提供的元数据 typeId `Microsoft.ServiceModel.Channels.Common.TypeMetadata`。</span><span class="sxs-lookup"><span data-stu-id="5069d-124">Resolves a supplied metadata typeId to a corresponding `Microsoft.ServiceModel.Channels.Common.TypeMetadata`.</span></span>|  
  
### <a name="to-implement-the-isoperationmetadatavalid-method"></a><span data-ttu-id="5069d-125">若要实现 IsOperationMetadataValid 方法</span><span class="sxs-lookup"><span data-stu-id="5069d-125">To implement the IsOperationMetadataValid method</span></span>  
  
1.  <span data-ttu-id="5069d-126">在解决方案资源管理器中双击**EchoAdapterMetadataResolverHandler.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="5069d-126">In Solution Explorer, double-click the **EchoAdapterMetadataResolverHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="5069d-127">在 Visual Studio 编辑器中，右键单击任意位置在编辑器内，在上下文菜单中，指向**大纲**，然后单击**停止大纲显示**。</span><span class="sxs-lookup"><span data-stu-id="5069d-127">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  
  
3.  <span data-ttu-id="5069d-128">在 Visual Studio 编辑器中，找到**IsOperationMetadataValid**方法，在此方法中，替换现有使用以下单个语句，以指示每个指定的操作元数据是否有效。</span><span class="sxs-lookup"><span data-stu-id="5069d-128">In the Visual Studio editor, find the **IsOperationMetadataValid** method, inside this method, replace the existing with the following single statement to indicate that every specified operation metadata is valid.</span></span>  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-istypemetadatavalid-method"></a><span data-ttu-id="5069d-129">若要实现 IsTypeMetadataValid 方法</span><span class="sxs-lookup"><span data-stu-id="5069d-129">To implement the IsTypeMetadataValid method</span></span>  
  
-   <span data-ttu-id="5069d-130">在 Visual Studio 编辑器中，找到**IsTypeMetadataValid**方法，在此方法中，替换现有使用以下单个语句，以指示每个指定的类型元数据是否有效。</span><span class="sxs-lookup"><span data-stu-id="5069d-130">In the Visual Studio editor, find the **IsTypeMetadataValid** method, inside this method, replace the existing with the following single statement to indicate that every specified type metadata is valid.</span></span>  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-resolveoperationmetadata-method"></a><span data-ttu-id="5069d-131">若要实现 ResolveOperationMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="5069d-131">To implement the ResolveOperationMetadata method</span></span>  
  
1.  <span data-ttu-id="5069d-132">在 Visual Studio 编辑器中，找到**ResolveOperationMetadata**方法，在此方法中，替换以下解决 OnReceiveEcho 操作，void OnReceiveEcho （Uri 路径，长 fileLength） 存在。</span><span class="sxs-lookup"><span data-stu-id="5069d-132">In the Visual Studio editor, find the **ResolveOperationMetadata** method, inside this method, replace the existing with the following to resolve the OnReceiveEcho operation, void OnReceiveEcho(Uri path, long fileLength).</span></span>  
  
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
  
2.  <span data-ttu-id="5069d-133">继续添加以下方法解决 Echo/EchoStrings 操作，string [] EchoStrings(string data)。</span><span class="sxs-lookup"><span data-stu-id="5069d-133">Continue adding the following to resolve the Echo/EchoStrings operation, string[] EchoStrings(string data).</span></span>  
  
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
  
3.  <span data-ttu-id="5069d-134">继续添加下面的逻辑解决 Echo/EchoStrings 操作，string [] EchoStrings(string data)。</span><span class="sxs-lookup"><span data-stu-id="5069d-134">Continue adding the following logic to resolve the Echo/EchoStrings operation, string[] EchoStrings(string data).</span></span>  
  
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
  
4.  <span data-ttu-id="5069d-135">继续添加下面的逻辑解决 CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath) 操作。</span><span class="sxs-lookup"><span data-stu-id="5069d-135">Continue adding the following logic to resolve the CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath) operation.</span></span>  
  
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
  
5.  <span data-ttu-id="5069d-136">继续添加以下内容以处理默认情况。</span><span class="sxs-lookup"><span data-stu-id="5069d-136">Continue adding the following to handle default case.</span></span>  
  
    ```csharp  
        default:  
            throw new AdapterException("Cannot resolve metadata for operation identifier " + operationId);  
    }  
    ```  
  
### <a name="to-implement-the-resolvetypemetadata-method"></a><span data-ttu-id="5069d-137">若要实现 ResolveTypeMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="5069d-137">To implement the ResolveTypeMetadata method</span></span>  
  
-   <span data-ttu-id="5069d-138">在 Visual Studio 编辑器中，找到**ResolveTypeMetadata**方法，在此方法中，替换为以下内容，以返回与现有`Microsoft.ServiceModel.Channels.Common.TypeMetadata`对象。</span><span class="sxs-lookup"><span data-stu-id="5069d-138">In the Visual Studio editor, find the **ResolveTypeMetadata** method, inside this method, replace the existing with the following to return a `Microsoft.ServiceModel.Channels.Common.TypeMetadata` object.</span></span>  
  
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
  
### <a name="to-define-the-custom-greeting-type-metadata-class"></a><span data-ttu-id="5069d-139">若要定义自定义问候语类型元数据类</span><span class="sxs-lookup"><span data-stu-id="5069d-139">To define the custom greeting type metadata class</span></span>  
  
1.  <span data-ttu-id="5069d-140">在解决方案资源管理器中右键单击**Echo 适配器**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="5069d-140">In Solution Explorer, right-click the **Echo Adapter** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="5069d-141">在中**添加新项**对话框中的**模板**，单击**类**。</span><span class="sxs-lookup"><span data-stu-id="5069d-141">In the **Add New Item** dialog box, under **Templates**, click **Class**.</span></span>  
  
3.  <span data-ttu-id="5069d-142">在中**名称**文本框中，键入**CustomGreetingTypeMetadata**。</span><span class="sxs-lookup"><span data-stu-id="5069d-142">In the **Name** text box, type **CustomGreetingTypeMetadata**.</span></span>  
  
4.  <span data-ttu-id="5069d-143">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="5069d-143">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="5069d-144">在 Visual Studio 编辑器中，使用以下替换现有代码：</span><span class="sxs-lookup"><span data-stu-id="5069d-144">In the Visual Studio editor, replace the existing code with the following:</span></span>  
  
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
  
6.  <span data-ttu-id="5069d-145">在 Visual Studio 中，从**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="5069d-145">In Visual Studio, from the **File** menu, click **Save All**.</span></span>  
  
### <a name="to-create-the-custom-greeting-xml-schema-definition"></a><span data-ttu-id="5069d-146">若要创建 XML 架构定义的自定义问候语</span><span class="sxs-lookup"><span data-stu-id="5069d-146">To create the custom greeting XML schema definition</span></span>  
  
1.  <span data-ttu-id="5069d-147">在解决方案资源管理器中右键单击**Echo 适配器**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="5069d-147">In Solution Explorer, right-click the **Echo Adapter** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="5069d-148">在中**添加新项**对话框中的**模板**，单击**XML 架构**。</span><span class="sxs-lookup"><span data-stu-id="5069d-148">In the **Add New Item** dialog box, under **Templates**, click **XML Schema**.</span></span>  
  
3.  <span data-ttu-id="5069d-149">在中**名称**文本框中，键入**CustomGreeting**。</span><span class="sxs-lookup"><span data-stu-id="5069d-149">In the **Name** text box, type **CustomGreeting**.</span></span>  
  
4.  <span data-ttu-id="5069d-150">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="5069d-150">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="5069d-151">在解决方案资源管理器中右键单击**CustomGreeting.xsd**文件，然后选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="5069d-151">In Solution Explorer, right-click the **CustomGreeting.xsd** file and choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="5069d-152">在 Visual Studio 编辑器中，首先使用开始 CustomGreeting 架构定义的以下代码替换现有代码：</span><span class="sxs-lookup"><span data-stu-id="5069d-152">In the Visual Studio editor, begin by replacing the existing code with the following code that begins the definition of the CustomGreeting schema:</span></span>  
  
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
  
     <span data-ttu-id="5069d-153">使用以下代码，开始 CustomGreeting 架构的定义：</span><span class="sxs-lookup"><span data-stu-id="5069d-153">with the following code that begins the definition of the CustomGreeting schema:</span></span>  
  
    ```csharp  
    <?xml version="1.0" encoding="utf-16"?>  
    <xsd:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" elementFormDefault="qualified" targetNamespace="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" xmlns:xsd ="http://www.w3.org/2001/XMLSchema">  
    ```  
  
7.  <span data-ttu-id="5069d-154">添加以下代码来定义 CustomGreeting 元素：</span><span class="sxs-lookup"><span data-stu-id="5069d-154">Add the following to define the CustomGreeting element:</span></span>  
  
    ```csharp  
    <xsd:element name="greeting" type="CustomGreeting" />  
    ```  
  
8.  <span data-ttu-id="5069d-155">现在添加 CustomGreeting 复杂类型的定义：</span><span class="sxs-lookup"><span data-stu-id="5069d-155">Now add the definition of the CustomGreeting complex type:</span></span>  
  
    ```csharp  
    <xsd:complexType name="CustomGreeting">  
      <xsd:sequence>  
        <xsd:element name="address" type="UsAddress" />  
        <xsd:element name="greetingText" type="xsd:string" />  
      </xsd:sequence>  
    </xsd:complexType>  
    ```  
  
9. <span data-ttu-id="5069d-156">继续 CustomGreeting 架构定义，添加 UsAddress 复杂类型：</span><span class="sxs-lookup"><span data-stu-id="5069d-156">Continue the CustomGreeting schema definition by adding the  UsAddress complex type:</span></span>  
  
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
  
10. <span data-ttu-id="5069d-157">通过添加邮政编码简单类型和架构的结束标记完成 CustomGreeting 架构的定义：</span><span class="sxs-lookup"><span data-stu-id="5069d-157">Complete the definition of the CustomGreeting schema by adding the PostalCode simple type and the closing tag for the schema:</span></span>  
  
    ```csharp  
      <xsd:simpleType name="PostalCode">  
        <xsd:restriction base="xsd:positiveInteger">  
          <xsd:pattern value="\d{5}" />  
        </xsd:restriction>  
      </xsd:simpleType>  
    </xsd:schema>  
    ```  
  
11. <span data-ttu-id="5069d-158">现在更新此文件的生成操作，因此它将被视为嵌入的资源。</span><span class="sxs-lookup"><span data-stu-id="5069d-158">Now update the build action for this file so it is treated as an embedded resource.</span></span> <span data-ttu-id="5069d-159">为此，请在 Visual Studio 解决方案窗格中，右键单击该文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="5069d-159">To do this, in the Visual Studio solution pane, right-click the file and choose **Properties**.</span></span> <span data-ttu-id="5069d-160">更改生成操作从**无**到**嵌入的资源**。</span><span class="sxs-lookup"><span data-stu-id="5069d-160">Change Build Action from **None** to **Embedded Resource**.</span></span>  
  
12. <span data-ttu-id="5069d-161">在 Visual Studio 中，从**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="5069d-161">In Visual Studio, from the **File** menu, click **Save All**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5069d-162">保存所做的工作。</span><span class="sxs-lookup"><span data-stu-id="5069d-162">You saved your work.</span></span> <span data-ttu-id="5069d-163">可以安全地关闭 Visual Studio 或转到下一步，[步骤 7:实现 Echo 适配器的同步出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5069d-163">You can safely close Visual Studio at this time or go to the next step, [Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="5069d-164">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="5069d-164">What Did I Just Do?</span></span>  
 <span data-ttu-id="5069d-165">只需实现解析 echo 适配器的功能的元数据。</span><span class="sxs-lookup"><span data-stu-id="5069d-165">You just implemented the metadata resolving capability for the echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5069d-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5069d-166">Next Steps</span></span>  
 <span data-ttu-id="5069d-167">在下一步，Echo 适配器实现出站的同步处理程序。</span><span class="sxs-lookup"><span data-stu-id="5069d-167">In the next step, you implement the synchronous outbound handler for the Echo Adapter.</span></span> <span data-ttu-id="5069d-168">您然后实现同步的入站处理程序，然后生成并部署 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="5069d-168">You then implement the synchronous inbound handler and then build and deploy the Echo Adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5069d-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="5069d-169">See Also</span></span>  
 <span data-ttu-id="5069d-170">[步骤 5：实现 Echo 适配器的元数据搜索处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5069d-170">[Step 5: Implement the Metadata Search Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md) </span></span>  
 <span data-ttu-id="5069d-171">[步骤 7：实现 Echo 适配器的同步出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5069d-171">[Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="5069d-172">教程 1:开发 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="5069d-172">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)