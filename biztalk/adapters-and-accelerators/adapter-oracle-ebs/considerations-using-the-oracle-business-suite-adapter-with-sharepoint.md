---
title: "与 SharePoint 使用 Oracle Business Suite 适配器的注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56de6267-ec34-4bd2-abd1-3f2b69876b36
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69f87b2971eeb9093257bc022ee12cdafed0dbf3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-using-the-oracle-business-suite-adapter-with-sharepoint"></a><span data-ttu-id="5bc48-102">与 SharePoint 使用 Oracle Business Suite 适配器的注意事项</span><span class="sxs-lookup"><span data-stu-id="5bc48-102">Considerations using the Oracle-Business Suite adapter with SharePoint</span></span>
<span data-ttu-id="5bc48-103">本主题包含有关的问题的信息时使用可能会遇到[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]与 Microsoft Office SharePoint Server，以及解决方法。</span><span class="sxs-lookup"><span data-stu-id="5bc48-103">This topic contains information about the issues you might encounter while using the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] with Microsoft Office SharePoint Server, along with resolutions.</span></span> <span data-ttu-id="5bc48-104">问题分为两个类别：</span><span class="sxs-lookup"><span data-stu-id="5bc48-104">The issues are divided into two categories:</span></span>  
  
-   <span data-ttu-id="5bc48-105">一般问题</span><span class="sxs-lookup"><span data-stu-id="5bc48-105">General issues</span></span>  
  
-   <span data-ttu-id="5bc48-106">涉及自定义 Web 部件的问题</span><span class="sxs-lookup"><span data-stu-id="5bc48-106">Issues involving custom Web Parts</span></span>  
  
## <a name="general-issues"></a><span data-ttu-id="5bc48-107">一般问题</span><span class="sxs-lookup"><span data-stu-id="5bc48-107">General Issues</span></span>  
 <span data-ttu-id="5bc48-108">本部分包含没有解决方法中的问题。</span><span class="sxs-lookup"><span data-stu-id="5bc48-108">This section contains issues that have no resolution.</span></span>  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="5bc48-109">问题 1： 不显示返回的 WCF 服务的简单类型数据</span><span class="sxs-lookup"><span data-stu-id="5bc48-109">Issue 1: The simple type data returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="5bc48-110">**说明**: Microsoft Office SharePoint Server 需要要进行的数据集或集合类型的 WCF 服务返回的数据。</span><span class="sxs-lookup"><span data-stu-id="5bc48-110">**Explanation**: Microsoft Office SharePoint Server expects the data returned by the WCF service to be of DataSet or Collection type only.</span></span> <span data-ttu-id="5bc48-111">如果 WCF 服务返回的数据的简单类型，Microsoft Office SharePoint Server 将不显示数据。</span><span class="sxs-lookup"><span data-stu-id="5bc48-111">If the data returned by the WCF service is of simple type, Microsoft Office SharePoint Server does not display the data.</span></span>  
  
 <span data-ttu-id="5bc48-112">**解析**： 没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="5bc48-112">**Resolution**: No resolution.</span></span> <span data-ttu-id="5bc48-113">它是一个与 Microsoft Office SharePoint Server 的已知的限制。</span><span class="sxs-lookup"><span data-stu-id="5bc48-113">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a><span data-ttu-id="5bc48-114">问题 2： 一条错误消息显示如果 WCF 服务返回的数据为 NULL</span><span class="sxs-lookup"><span data-stu-id="5bc48-114">Issue 2: An error message is displayed if the data returned by the WCF service is NULL</span></span>  
 <span data-ttu-id="5bc48-115">**说明**： 如果 WCF 服务返回的数据为 NULL 值，Microsoft Office SharePoint Server 将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="5bc48-115">**Explanation**: If the data returned by the WCF service is a NULL value, Microsoft Office SharePoint Server displays an error message.</span></span> <span data-ttu-id="5bc48-116">例如，假设你正在使用业务数据列表 Web 部件**Finder**方法实例，并在 Oracle E-business Suite 客户根据搜索表达式搜索。</span><span class="sxs-lookup"><span data-stu-id="5bc48-116">For example, suppose you are using the Business Data List Web Part for the **Finder** method instance, and are searching for customers in Oracle E-Business Suite based on a search expression.</span></span> <span data-ttu-id="5bc48-117">你指定的搜索表达式提取一个 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="5bc48-117">The search expression that you specified fetches a NULL value.</span></span> <span data-ttu-id="5bc48-118">在这种情况下，Microsoft Office SharePoint Server 将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="5bc48-118">In this case, Microsoft Office SharePoint Server will display an error message.</span></span>  
  
 <span data-ttu-id="5bc48-119">**解析**： 没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="5bc48-119">**Resolution**: No resolution.</span></span> <span data-ttu-id="5bc48-120">它是一个与 Microsoft Office SharePoint Server 的已知的限制。</span><span class="sxs-lookup"><span data-stu-id="5bc48-120">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="5bc48-121">问题 3: WCF 服务返回的简单类型的数组不显示</span><span class="sxs-lookup"><span data-stu-id="5bc48-121">Issue 3: An array of simple type returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="5bc48-122">**说明**： 如果 WCF 服务返回的数据是简单类型的数组，Microsoft Office SharePoint Server 将不显示数据。</span><span class="sxs-lookup"><span data-stu-id="5bc48-122">**Explanation**: If the data returned by the WCF service is an array of simple type, Microsoft Office SharePoint Server does not display the data.</span></span> <span data-ttu-id="5bc48-123">此外，在业务数据目录定义编辑器中返回数组的简单类型执行的方法实例时，会显示以下错误消息:"后端系统适配器返回一个结构使用的相应的元数据 （不兼容实例，但、 参数或 TypeDescriptor）。"</span><span class="sxs-lookup"><span data-stu-id="5bc48-123">Moreover, when you execute a method instance in Business Data Catalog Definition Editor that returns an array of simple type, the following error message is displayed: “Backend system adapter returned a structure incompatible with the corresponding metadata (MethodInstance, Parameter or TypeDescriptor).”</span></span>  
  
 <span data-ttu-id="5bc48-124">**解析**： 没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="5bc48-124">**Resolution**: No resolution.</span></span> <span data-ttu-id="5bc48-125">它是使用 Microsoft Office SharePoint Server 和业务数据目录定义编辑器已知的限制。</span><span class="sxs-lookup"><span data-stu-id="5bc48-125">It is a known limitation with Microsoft Office SharePoint Server and Business Data Catalog Definition Editor.</span></span>  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a><span data-ttu-id="5bc48-126">问题 4： 无法导入一个包含具有大于 300 个字段的复杂类型形参的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="5bc48-126">Issue 4: Cannot import an application definition file that contains a complex type parameter having more than 300 fields</span></span>  
 <span data-ttu-id="5bc48-127">**说明**: Microsoft Office SharePoint Server 无法导入具有 WCF 服务返回的复杂类型参数中的大于 300 个字段并显示一条错误消息，如果你尝试执行此操作的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="5bc48-127">**Explanation**: Microsoft Office SharePoint Server cannot import an application definition file that has more than 300 fields in the complex type parameter returned by the WCF service, and displays an error message if you try to do so.</span></span> <span data-ttu-id="5bc48-128">这是因为 Microsoft Office SharePoint Server 无法显示大于 300 个字段的复杂类型参数的限制。</span><span class="sxs-lookup"><span data-stu-id="5bc48-128">This is due to the limitation of Microsoft Office SharePoint Server of not being able to display more than 300 fields of a complex type parameter.</span></span>  
  
 <span data-ttu-id="5bc48-129">**解析**： 使用业务数据目录定义编辑器来限制小于或等于 300 的复杂类型参数的字段数。</span><span class="sxs-lookup"><span data-stu-id="5bc48-129">**Resolution**: Use the Business Data Catalog Definition Editor to limit the number of fields of the complex type parameter to less than or equal to 300.</span></span> <span data-ttu-id="5bc48-130">具体取决于你的需求，你可以删除复杂类型参数在业务数据目录定义编辑器中，不需要 Microsoft Office SharePoint Server 中显示的字段。</span><span class="sxs-lookup"><span data-stu-id="5bc48-130">Depending on your requirement, you can delete the fields of the complex type parameter in the Business Data Catalog Definition Editor that you do not require to be displayed in Microsoft Office SharePoint Server.</span></span>  <span data-ttu-id="5bc48-131">或者，你可以在其中还将应用程序定义文件从业务数据目录定义编辑器导出了所有字段，，然后修改在记事本或任何 XML 创作应用程序以删除不是字段中的应用程序定义文件需要限制和 300 之间的字段数。</span><span class="sxs-lookup"><span data-stu-id="5bc48-131">Alternatively, you can also export the application definition file from Business Data Catalog Definition Editor with all the fields, and then modify the application definition file in a notepad or any XML authoring application to delete the fields that are not required in order to limit the number of fields to 300.</span></span>  
  
##  <a name="Custom_Web_Part"></a><span data-ttu-id="5bc48-132">涉及自定义 Web 部件的问题</span><span class="sxs-lookup"><span data-stu-id="5bc48-132">Issues Involving Custom Web Parts</span></span>  
 <span data-ttu-id="5bc48-133">本部分包含有关解决方法需要自定义 Web 部件使用的问题。</span><span class="sxs-lookup"><span data-stu-id="5bc48-133">This section contains issues that require the use of custom Web Part for a resolution.</span></span> <span data-ttu-id="5bc48-134">有关使用自定义 Web 部件以解决在使用时可能出现的问题的详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]和 Microsoft Office SharePoint Server，请参阅[如何通过 Oracle E-business Suite 中使用自定义 web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc48-134">For detailed information about using a custom Web Part to resolve issues that might come up while working with [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] and Microsoft Office SharePoint Server, see [How to use a custom web part with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md).</span></span>  
  
###  <a name="Issue1"></a><span data-ttu-id="5bc48-135">问题 1： 基于多个值的限制与 Microsoft Office SharePoint Server 中显示一条记录</span><span class="sxs-lookup"><span data-stu-id="5bc48-135">Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values</span></span>  
 <span data-ttu-id="5bc48-136">**说明**： 如果你想要从 Oracle E-business Suite 的多个值 （输入参数） 为基础的 Microsoft Office SharePoint Server 中显示一条记录，则无法使用任何三个 Web 部件 (业务数据列表中，业务数据项和业务数据的相关的列表） 指定在步骤 3： 创建一个 SharePoint 应用程序检索数据从 Oracle E-business Suite 中[教程： 呈现数据的 SharePoint 站点上的 Oracle E-business Suite](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc48-136">**Explanation**: If you want to display a single record in Microsoft Office SharePoint Server based on multiple values (input parameters) from Oracle E-Business Suite, you cannot use any of the three Web Parts (Business Data List, Business Data Item, and Business Data Related List) specified in Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite in [Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).</span></span>  
  
 <span data-ttu-id="5bc48-137">**解析**： 你必须使用自定义 Web 部件执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5bc48-137">**Resolution**: You must use a custom Web Part to do this.</span></span> <span data-ttu-id="5bc48-138">有关使用自定义 Web 部件的信息，请参阅[如何通过 Oracle E-business Suite 中使用自定义 web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc48-138">For information about using a custom Web Part, see [How to use a custom web part with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md).</span></span> <span data-ttu-id="5bc48-139">在"步骤 1:: 创建自定义 Web 部件"该主题的你可以在步骤 5 中使用下面的代码示例。</span><span class="sxs-lookup"><span data-stu-id="5bc48-139">In “Step 1: Create a Custom Web Part” of that topic, you can use the following code sample in step 5.</span></span> <span data-ttu-id="5bc48-140">下面的代码示例采用 BankCountry 和 BankKey 作为输入参数，然后将其显示为 Microsoft Office SharePoint Server 中的单个记录。</span><span class="sxs-lookup"><span data-stu-id="5bc48-140">The following code sample takes BankCountry and BankKey as the input parameters, and then displays them as a single record in Microsoft Office SharePoint Server.</span></span>  
  
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
>  <span data-ttu-id="5bc48-141">应用程序定义文件必须包含**特定的 Finder**方法实例。</span><span class="sxs-lookup"><span data-stu-id="5bc48-141">The application definition file must contain the **Specific Finder** method instance.</span></span> <span data-ttu-id="5bc48-142">A**特定的 Finder**方法找到了一个基于标识符的特定记录。</span><span class="sxs-lookup"><span data-stu-id="5bc48-142">A **Specific Finder** method finds a specific record based on an identifier.</span></span> <span data-ttu-id="5bc48-143">有关创建信息**特定的 Finder**方法实例时，请参阅中的"要求 2:: 检索详细信息的特定客户从列表的客户"[步骤 2： 创建应用程序定义文件Oracle E-business Suite 项目](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)中[教程： 呈现数据的 SharePoint 站点上的 Oracle E-business Suite](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc48-143">For information about creating a **Specific Finder** method instance, see “Requirement 2: Retrieve Details for a Specific Customer from the List of Customers” in [Step 2: Create an application definition file for the Oracle E-Business Suite artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md) in [Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).</span></span>  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a><span data-ttu-id="5bc48-144">问题 2： 不能指定对数组元素的值</span><span class="sxs-lookup"><span data-stu-id="5bc48-144">Issue 2: Cannot specify values to array elements</span></span>  
 <span data-ttu-id="5bc48-145">**说明**: WCF 服务的输入的参数是一个数组，如果你不能指定到使用在创建使用业务数据目录定义编辑器的应用程序定义文件中定义的筛选器的数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="5bc48-145">**Explanation**: If the input parameter of the WCF service is an array, you cannot specify values to the array elements using filters that are defined in the application definition file created using the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="5bc48-146">这意味着，你不能用于业务数据列表或业务数据项 Web 部件在 Microsoft Office SharePoint Server 中指定这些到 WCF 服务的输入参数 （数组的元素） 的值。</span><span class="sxs-lookup"><span data-stu-id="5bc48-146">It implies that you cannot use the Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server to specify values for these input parameters (elements of array) to the WCF service.</span></span> <span data-ttu-id="5bc48-147">这是由于应用程序定义文件中定义数组的方法。</span><span class="sxs-lookup"><span data-stu-id="5bc48-147">This is because of the way arrays are defined in the application definition file.</span></span>  
  
 <span data-ttu-id="5bc48-148">**解析**： 使用自定义 Web 部件将值分配到数组元素。</span><span class="sxs-lookup"><span data-stu-id="5bc48-148">**Resolution**: Use a custom Web Part to assign values to array elements.</span></span> <span data-ttu-id="5bc48-149">有关使用自定义 Web 部件的信息，请参阅[如何通过 Oracle E-business Suite 中使用自定义 web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc48-149">For information about using a custom Web Part, see [How to use a custom web part with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md).</span></span> <span data-ttu-id="5bc48-150">例如，可以使用下面的代码示例中的步骤 3 中"问题 1： 在 Microsoft Office SharePoint Server 中显示的单个记录限制基于多个值"将值分配到数组元素。</span><span class="sxs-lookup"><span data-stu-id="5bc48-150">For example, you can use the following code sample in step 3 in “Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values” to assign values to array elements.</span></span>  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a><span data-ttu-id="5bc48-151">指定给复杂类型参数的 NULL 值的问题 3： 限制</span><span class="sxs-lookup"><span data-stu-id="5bc48-151">Issue 3: Limitation with specifying NULL values to complex type parameters</span></span>  
 <span data-ttu-id="5bc48-152">**说明**： 如果 Microsoft Office SharePoint Server 中不指定任何值为复杂类型参数从 Web 部件，NULL 应传递为复杂类型参数的值到 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="5bc48-152">**Explanation**: If you do not specify any value for a complex type parameter from a Web Part in Microsoft Office SharePoint Server, NULL should be passed on as the value for the complex type parameter to the WCF service.</span></span> <span data-ttu-id="5bc48-153">但是，非 NULL 值传递为复杂类型参数，并且为其子元素 （的简单类型） 传递了 NULL。</span><span class="sxs-lookup"><span data-stu-id="5bc48-153">However, a non-NULL value is passed for the complex type parameter, and NULL is passed for its children elements (of simple type).</span></span> <span data-ttu-id="5bc48-154">这将导致预期的消息架构与传递到 WCF 服务的消息架构不匹配。</span><span class="sxs-lookup"><span data-stu-id="5bc48-154">This causes a mismatch between the expected message schema and the message schema that is passed on to the WCF service.</span></span> <span data-ttu-id="5bc48-155">因此，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可能会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="5bc48-155">As a result, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] might display an error message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bc48-156">若要了解复杂类型参数的默认值，当从 Microsoft Office SharePoint Server 中的 Web 部件不传递任何值，请使用步骤 2 中的代码示例中所述"问题 1： 使用 Microsoft Office SharePoint Server 中显示一条记录的限制基于多个值。"</span><span class="sxs-lookup"><span data-stu-id="5bc48-156">To find out the default value of a complex type parameter when no value is passed from a Web Part in Microsoft Office SharePoint Server, use step 2 in the code sample mentioned in “Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values.”</span></span>  
  
 <span data-ttu-id="5bc48-157">**解析**： 使用自定义 Web 部件将 NULL 值分配给复杂类型参数。</span><span class="sxs-lookup"><span data-stu-id="5bc48-157">**Resolution**: Use a custom Web Part to assign a NULL value to the complex type parameter.</span></span> <span data-ttu-id="5bc48-158">有关使用自定义 Web 部件的信息，请参阅[如何通过 Oracle E-business Suite 中使用自定义 web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc48-158">For information about using a custom Web Part, see [How to use a custom web part with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc48-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bc48-159">See Also</span></span>  
[<span data-ttu-id="5bc48-160">使用带有 SharePoint Oracle E-business Suite 适配器</span><span class="sxs-lookup"><span data-stu-id="5bc48-160">Use the Oracle E-Business Suite adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)