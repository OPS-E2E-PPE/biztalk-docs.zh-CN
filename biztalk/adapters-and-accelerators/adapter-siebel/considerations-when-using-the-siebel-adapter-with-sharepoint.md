---
title: 与 SharePoint 结合使用 Siebel 适配器时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea7da079-3250-4ecc-bf01-6b5495c7f380
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee3328ea53a68688441c25c254a73e45cb94f083
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371778"
---
# <a name="considerations-when-using-the-siebel-adapter-with-sharepoint"></a><span data-ttu-id="a608d-102">与 SharePoint 结合使用 Siebel 适配器时的注意事项</span><span class="sxs-lookup"><span data-stu-id="a608d-102">Considerations when using the Siebel adapter with SharePoint</span></span>
<span data-ttu-id="a608d-103">本主题包含有关的问题的信息可能会遇到同时使用[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]使用 Microsoft Office SharePoint Server，以及解决方法。</span><span class="sxs-lookup"><span data-stu-id="a608d-103">This topic contains information about the issues you might encounter while using the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] with Microsoft Office SharePoint Server, along with resolutions.</span></span> <span data-ttu-id="a608d-104">问题分为两个类别：</span><span class="sxs-lookup"><span data-stu-id="a608d-104">The issues are divided into two categories:</span></span>  
  
-   <span data-ttu-id="a608d-105">常规问题</span><span class="sxs-lookup"><span data-stu-id="a608d-105">General issues</span></span>  
  
-   <span data-ttu-id="a608d-106">涉及自定义 Web 部件的问题</span><span class="sxs-lookup"><span data-stu-id="a608d-106">Issues involving custom Web Parts</span></span>  
  
## <a name="general-issues"></a><span data-ttu-id="a608d-107">一般问题</span><span class="sxs-lookup"><span data-stu-id="a608d-107">General Issues</span></span>  
 <span data-ttu-id="a608d-108">本部分包含有没有解决方法，或需要修改应用程序定义文件，解决的问题。</span><span class="sxs-lookup"><span data-stu-id="a608d-108">This section contains issues that either have no resolution or requires you to modify the application definition file for the resolution.</span></span>  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="a608d-109">问题 1:不显示 WCF 服务返回简单类型数据</span><span class="sxs-lookup"><span data-stu-id="a608d-109">Issue 1: The simple type data returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="a608d-110">**说明**:Microsoft Office SharePoint Server 需要为数据集或集合类型的 WCF 服务返回的数据。</span><span class="sxs-lookup"><span data-stu-id="a608d-110">**Explanation**: Microsoft Office SharePoint Server expects the data returned by the WCF service to be of DataSet or Collection type only.</span></span> <span data-ttu-id="a608d-111">如果 WCF 服务返回的数据的简单类型，则 Microsoft Office SharePoint Server 不显示数据。</span><span class="sxs-lookup"><span data-stu-id="a608d-111">If the data returned by the WCF service is of simple type, Microsoft Office SharePoint Server does not display the data.</span></span>  
  
 <span data-ttu-id="a608d-112">**解析**:没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="a608d-112">**Resolution**: No resolution.</span></span> <span data-ttu-id="a608d-113">这是一个使用 Microsoft Office SharePoint Server 的已知的限制。</span><span class="sxs-lookup"><span data-stu-id="a608d-113">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a><span data-ttu-id="a608d-114">问题 2:如果 WCF 服务返回的数据为 NULL，将显示一条错误消息</span><span class="sxs-lookup"><span data-stu-id="a608d-114">Issue 2: An error message is displayed if the data returned by the WCF service is NULL</span></span>  
 <span data-ttu-id="a608d-115">**说明**:如果 WCF 服务返回的数据为 NULL 值，Microsoft Office SharePoint Server 将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a608d-115">**Explanation**: If the data returned by the WCF service is a NULL value, Microsoft Office SharePoint Server displays an error message.</span></span> <span data-ttu-id="a608d-116">例如，假设要使用的业务数据列表 Web 部件**Finder**方法实例，并在搜索表达式所基于的 Siebel 系统中进行搜索的客户。</span><span class="sxs-lookup"><span data-stu-id="a608d-116">For example, suppose you are using the Business Data List Web Part for the **Finder** method instance, and are searching for customers in the Siebel system based on a search expression.</span></span> <span data-ttu-id="a608d-117">指定的搜索表达式中提取一个 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="a608d-117">The search expression that you specified fetches a NULL value.</span></span> <span data-ttu-id="a608d-118">在这种情况下，Microsoft Office SharePoint Server 将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a608d-118">In this case, Microsoft Office SharePoint Server will display an error message.</span></span>  
  
 <span data-ttu-id="a608d-119">**解析**:没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="a608d-119">**Resolution**: No resolution.</span></span> <span data-ttu-id="a608d-120">这是一个使用 Microsoft Office SharePoint Server 的已知的限制。</span><span class="sxs-lookup"><span data-stu-id="a608d-120">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="a608d-121">问题 3:不显示 WCF 服务返回简单类型的数组</span><span class="sxs-lookup"><span data-stu-id="a608d-121">Issue 3: An array of simple type returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="a608d-122">**说明**:如果 WCF 服务返回的数据是简单类型的数组，Microsoft Office SharePoint Server 将不显示数据。</span><span class="sxs-lookup"><span data-stu-id="a608d-122">**Explanation**: If the data returned by the WCF service is an array of simple type, Microsoft Office SharePoint Server does not display the data.</span></span> <span data-ttu-id="a608d-123">此外，在执行方法实例中 Business Data Catalog Definition Editor 返回简单类型的数组时，将显示以下错误消息："后端系统适配器返回结构与相应的元数据 （MethodInstance、 参数或 TypeDescriptor） 不兼容。"</span><span class="sxs-lookup"><span data-stu-id="a608d-123">Moreover, when you execute a method instance in Business Data Catalog Definition Editor that returns an array of simple type, the following error message is displayed: “Backend system adapter returned a structure incompatible with the corresponding metadata (MethodInstance, Parameter or TypeDescriptor).”</span></span>  
  
 <span data-ttu-id="a608d-124">**解析**:没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="a608d-124">**Resolution**: No resolution.</span></span> <span data-ttu-id="a608d-125">它是使用 Microsoft Office SharePoint Server 和 Business Data Catalog Definition Editor 已知的限制。</span><span class="sxs-lookup"><span data-stu-id="a608d-125">It is a known limitation with Microsoft Office SharePoint Server and Business Data Catalog Definition Editor.</span></span>  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a><span data-ttu-id="a608d-126">问题 4:无法导入包含复杂类型参数都有 300 多个字段的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="a608d-126">Issue 4: Cannot import an application definition file that contains a complex type parameter having more than 300 fields</span></span>  
 <span data-ttu-id="a608d-127">**说明**:Microsoft Office SharePoint Server 无法导入应用程序定义文件中的 WCF 服务，返回的复杂类型参数的 300 多个字段并显示一条错误消息，如果您尝试执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a608d-127">**Explanation**: Microsoft Office SharePoint Server cannot import an application definition file that has more than 300 fields in the complex type parameter returned by the WCF service, and displays an error message if you try to do so.</span></span> <span data-ttu-id="a608d-128">这是因为不能够显示 300 多个字段的复杂类型参数的 Microsoft Office SharePoint Server 的限制。</span><span class="sxs-lookup"><span data-stu-id="a608d-128">This is due to the limitation of Microsoft Office SharePoint Server of not being able to display more than 300 fields of a complex type parameter.</span></span>  
  
 <span data-ttu-id="a608d-129">**解析**:使用 Business Data Catalog Definition Editor 可限制小于或等于 300 的复杂类型参数的字段的数目。</span><span class="sxs-lookup"><span data-stu-id="a608d-129">**Resolution**: Use the Business Data Catalog Definition Editor to limit the number of fields of the complex type parameter to less than or equal to 300.</span></span> <span data-ttu-id="a608d-130">具体取决于你的要求，可以删除复杂类型参数在 Business Data Catalog Definition Editor 不需要 Microsoft Office SharePoint Server 中显示的字段。</span><span class="sxs-lookup"><span data-stu-id="a608d-130">Depending on your requirement, you can delete the fields of the complex type parameter in the Business Data Catalog Definition Editor that you do not require to be displayed in Microsoft Office SharePoint Server.</span></span>  <span data-ttu-id="a608d-131">或者，您可以还将应用程序定义文件从 Business Data Catalog Definition Editor 导出所有字段，然后修改在记事本或任何 XML 创作应用程序以删除不是字段中的应用程序定义文件必须以限制为 300 的字段数。</span><span class="sxs-lookup"><span data-stu-id="a608d-131">Alternatively, you can also export the application definition file from Business Data Catalog Definition Editor with all the fields, and then modify the application definition file in a notepad or any XML authoring application to delete the fields that are not required in order to limit the number of fields to 300.</span></span>  
  
##  <a name="Custom_Web_Part"></a> <span data-ttu-id="a608d-132">涉及自定义 Web 部件的问题</span><span class="sxs-lookup"><span data-stu-id="a608d-132">Issues Involving Custom Web Parts</span></span>  
 <span data-ttu-id="a608d-133">本部分包含用于解析都需要使用自定义 Web 部件的问题。</span><span class="sxs-lookup"><span data-stu-id="a608d-133">This section contains issues that require the use of custom Web Parts for resolution.</span></span> <span data-ttu-id="a608d-134">有关使用自定义 Web 部件以解决可能会使用时产生的问题的详细信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和 Microsoft Office SharePoint Server，请参阅[Siebel 适配器一起使用自定义 Web 部件](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a608d-134">For detailed information about using a custom Web Part to resolve issues that might come up while working with [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and Microsoft Office SharePoint Server, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span>  
  
### <a name="issue-1-index-of-an-enumerator-is-displayed-instead-of-the-value-for-the-enum-data-type"></a><span data-ttu-id="a608d-135">问题 1:一个枚举器的索引显示而不是枚举数据类型的值</span><span class="sxs-lookup"><span data-stu-id="a608d-135">Issue 1: Index of an enumerator is displayed instead of the value for the enum data type</span></span>  
 <span data-ttu-id="a608d-136">**说明**:如果 Microsoft Office SharePoint Server 中的业务数据项 Web 部件或业务数据列表包含枚举类型 （一组称为枚举器的命名常量组成的不同类型） 的数据，而不是其值中显示的枚举器的索引Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="a608d-136">**Explanation**: If a Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server contains data of enum type (a distinct type consisting of a set of named constants called the enumerators), the index of the enumerator is displayed instead of its value in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="a608d-137">这是因为业务数据列表和业务数据 Web 部件未正确打印到 SharePoint 门户的枚举类型数据的值。</span><span class="sxs-lookup"><span data-stu-id="a608d-137">This is because the Business Data List and Business Data Item Web Parts incorrectly print the values of the enum type data to the SharePoint portal.</span></span>  
  
 <span data-ttu-id="a608d-138">**解析**:使用自定义 Web 部件来打印而不是索引的枚举器的值。</span><span class="sxs-lookup"><span data-stu-id="a608d-138">**Resolution**: Use a custom Web Part to print the value of the enumerator instead of the index.</span></span> <span data-ttu-id="a608d-139">有关使用自定义 Web 部件的信息，请参阅[Siebel 适配器一起使用自定义 Web 部件](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a608d-139">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="a608d-140">例如，可以在 Web 部件中使用下面的代码示例可在 Microsoft Office SharePoint Server 上打印的枚举类型数据的正确值。</span><span class="sxs-lookup"><span data-stu-id="a608d-140">For example, you can use the following code sample in your Web part to print the correct values of enum type data on Microsoft Office SharePoint Server.</span></span>  
  
```  
namespace CustomWebpart  
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
            string SearchExpr = "[Address Name] LIKE \"*\"";  
            object ElementType = null;  
  
/***Step 1: Get the required entity and method.***/  
  
            LobSystem newSystem = ApplicationRegistry.GetLobSystems()["WebServiceLobSystem"]; // Name specified in application definition file  
            LobSystemInstance newSystemInstance = newSystem.GetLobSystemInstances()["Siebel_Instance"]; // Name specified in application definition file  
            Entity CategoryEntity = newSystem.GetEntities()["Siebel_Method_Name"]; // Name specified in application definition file  
            Method newMethod = CategoryEntity.GetMethods()["Query"]; // Name specified in application definition file  
            MethodInstance methodInstance = newMethod.GetMethodInstances()["MethodInstance0"]; // Name specified in application definition file  
  
/***Step 2: Get the list of input parameters.***/  
            Object[] args = methodInstance.GetMethod().CreateDefaultParameterInstances(methodInstance); // Get default value of the input parameter  
            Object[] ArgsInput = new Object[args.Length];  
  
/***Step 3: Assign them required values.***/  
  
           //Assigning values to a complex type parameter. Index of this parameter is 3rd in args array.   
           /*** Complex Type Parameter is defined as follows:  
           <Parameter Direction="In" Name="BusinessAddressQueryInputRecord">  
           <TypeDescriptor TypeName="BDC.BusinessAddressQueryInputRecord,WebServiceLobSystem" Name="BusinessAddressQueryInputRecord">  
              <TypeDescriptors>  
                 <TypeDescriptor TypeName="System.String, ...." Name="SearchExpr"></TypeDescriptor>  
                 <TypeDescriptor TypeName="System.String, ...." Name="SortSpec"></TypeDescriptor>  
                 <TypeDescriptor TypeName="System.String[], ...." IsCollection="true" Name="QueryFields"></TypeDescriptor>  
              </TypeDescriptors>  
           </TypeDescriptor>  
           </Parameter>  
            * We are assigning value to Parameter SearchExpr. ***/  
  
            Assembly asm = Assembly.GetAssembly(args[2].GetType());  
            Type t = asm.GetType(args[2].GetType().ToString()); // Get type of the parameter  
  
            FieldInfo[] FI = t.GetFields();  
            ElementType = Activator.CreateInstance(t);  
            ElementType.GetType().GetFields()[0].SetValue(ElementType, (Object)SearchExpr);  
  
            ArgsInput[2] = ElementType; // ArgsInput is fed as input while executing Method Instance.  
  
/***Step 4: Execute the particular method instance using the required value.***/              
  
            IEntityInstanceEnumerator prodEntityInstanceEnumerator = (IEntityInstanceEnumerator)CategoryEntity.Execute(methodInstance, newSystemInstance, ref ArgsInput); //Method instance of type Finder is being used here.  
  
/***Step 5: Display the output on the custom Web Part in Microsoft Office SharePoint Server.***/  
  
            writer.Write("<table>");  
            while (prodEntityInstanceEnumerator.MoveNext())  
            {  
                IEntityInstance IE = prodEntityInstanceEnumerator.Current;  
  
                writer.Write("<tr>");  
                foreach (Field f in CategoryEntity.GetFinderView().Fields)  
                {  
  
                    writer.Write("<td>");  
                    writer.Write(IE[f]);  
                    writer.Write("</td>");  
                }  
                writer.Write("</tr>");  
            }  
            writer.Write("</table>");  
  
        }  
    }  
}  
  
```  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a><span data-ttu-id="a608d-141">问题 2:不能指定为数组元素的值</span><span class="sxs-lookup"><span data-stu-id="a608d-141">Issue 2: Cannot specify values to array elements</span></span>  
 <span data-ttu-id="a608d-142">**说明**:如果 WCF 服务的输入的参数是一个数组，则无法指定使用在使用 Business Data Catalog Definition Editor 创建的应用程序定义文件中定义的筛选器的数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="a608d-142">**Explanation**: If the input parameter of the WCF service is an array, you cannot specify values to the array elements using filters that are defined in the application definition file created using the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="a608d-143">这意味着，您不能使用的业务数据列表或业务数据 Web 部件在 Microsoft Office SharePoint Server 中指定这些输入参数 （数组的元素） 的 WCF 服务的值。</span><span class="sxs-lookup"><span data-stu-id="a608d-143">It implies that you cannot use the Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server to specify values for these input parameters (elements of array) to the WCF service.</span></span> <span data-ttu-id="a608d-144">这是因为应用程序定义文件中定义数组的方式。</span><span class="sxs-lookup"><span data-stu-id="a608d-144">This is because of the way arrays are defined in the application definition file.</span></span>  
  
 <span data-ttu-id="a608d-145">**解析**:使用自定义 Web 部件将值分配给数组元素。</span><span class="sxs-lookup"><span data-stu-id="a608d-145">**Resolution**: Use a custom Web Part to assign values to array elements.</span></span> <span data-ttu-id="a608d-146">有关使用自定义 Web 部件的信息，请参阅[Siebel 适配器一起使用自定义 Web 部件](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a608d-146">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="a608d-147">例如，可以使用下面的代码示例中的步骤 3 中"问题 1:一个枚举器的索引而不是枚举数据类型的值显示"将值分配到数组元素。</span><span class="sxs-lookup"><span data-stu-id="a608d-147">For example, you can use the following code sample in step 3 in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type” to assign values to array elements.</span></span>  
  
```  
/***Assign required values to parameters of type array.***/   
/***Assumption is that the ith parameter of Method is of type Array and all the simple type elements in the array are of type string***/  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a><span data-ttu-id="a608d-148">问题 3:指定到复杂类型参数的 NULL 值的限制</span><span class="sxs-lookup"><span data-stu-id="a608d-148">Issue 3: Limitation with specifying NULL values to complex type parameters</span></span>  
 <span data-ttu-id="a608d-149">**说明**:如果 Microsoft Office SharePoint Server 中不指定 Web 部件中的一个复杂类型参数的任何值，NULL 应传递复杂类型参数的值作为到 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="a608d-149">**Explanation**: If you do not specify any value for a complex type parameter from a Web Part in Microsoft Office SharePoint Server, NULL should be passed on as the value for the complex type parameter to the WCF service.</span></span> <span data-ttu-id="a608d-150">但是，为复杂类型参数，传递了非 NULL 值和 NULL 传递 （的简单类型） 及其子元素。</span><span class="sxs-lookup"><span data-stu-id="a608d-150">However, a non-NULL value is passed for the complex type parameter, and NULL is passed for its children elements (of simple type).</span></span> <span data-ttu-id="a608d-151">这将导致预期的消息架构传递给 WCF 服务的消息架构不匹配。</span><span class="sxs-lookup"><span data-stu-id="a608d-151">This causes a mismatch between the expected message schema and the message schema that is passed on to the WCF service.</span></span> <span data-ttu-id="a608d-152">因此，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可能会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a608d-152">As a result, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] might display an error message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a608d-153">若要从 Microsoft Office SharePoint Server 中的 Web 部件不传递任何值时，找出复杂类型参数的默认值，请使用步骤 2 中的代码示例中所述"问题 1:枚举器的显示索引而不是枚举数据类型的值。"</span><span class="sxs-lookup"><span data-stu-id="a608d-153">To find out the default value of a complex type parameter when no value is passed from a Web Part in Microsoft Office SharePoint Server, use step 2 in the code sample mentioned in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type.”</span></span>  
  
 <span data-ttu-id="a608d-154">**解析**:使用自定义 Web 部件时从 Microsoft Office SharePoint Server 中的 Web 部件未不指定任何值为复杂类型参数分配一个 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="a608d-154">**Resolution**: Use a custom Web Part to assign a NULL value to the complex type parameter when no value is specified from a Web Part in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="a608d-155">有关使用自定义 Web 部件的信息，请参阅[Siebel 适配器一起使用自定义 Web 部件](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a608d-155">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span>  
  
###  <a name="Issue1"></a> <span data-ttu-id="a608d-156">问题 4:在 Microsoft Office SharePoint Server 中显示一条记录限制基于多个值</span><span class="sxs-lookup"><span data-stu-id="a608d-156">Issue 4: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values</span></span>  
 <span data-ttu-id="a608d-157">**说明**:如果你想要在基于多个值 （输入参数） 从 Siebel 系统的 Microsoft Office SharePoint Server 中显示一条记录，则无法使用所有三个 Web 部件 （业务数据列表中，业务数据项和业务数据相关列表） 指定在[步骤 3:创建 SharePoint 应用程序以从 Siebel 检索数据](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)在[教程 1:从 SharePoint 站点上的 Siebel 系统提供数据](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)。</span><span class="sxs-lookup"><span data-stu-id="a608d-157">**Explanation**: If you want to display a single record in Microsoft Office SharePoint Server based on multiple values (input parameters) from a Siebel system, you cannot use any of the three Web Parts (Business Data List, Business Data Item, and Business Data Related List) specified in [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) in [Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).</span></span>  
  
 <span data-ttu-id="a608d-158">**解析**:必须使用自定义 Web 部件来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a608d-158">**Resolution**: You must use a custom Web Part to do this.</span></span> <span data-ttu-id="a608d-159">有关使用自定义 Web 部件的信息，请参阅[Siebel 适配器一起使用自定义 Web 部件](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a608d-159">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="a608d-160">例如，在步骤 3 中"问题 1:一个枚举器的索引而不是枚举数据类型的值显示"可以修改代码以提供多个而不是提供单个业务组件参数的输入参数的值。</span><span class="sxs-lookup"><span data-stu-id="a608d-160">For example, in step 3 in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type” you can modify the code to provide values for more than one parameter instead of providing input to a single business component parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a608d-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="a608d-161">See Also</span></span>  
 [<span data-ttu-id="a608d-162">使用 Siebel 适配器和 SharePoint</span><span class="sxs-lookup"><span data-stu-id="a608d-162">Use the Siebel Adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)