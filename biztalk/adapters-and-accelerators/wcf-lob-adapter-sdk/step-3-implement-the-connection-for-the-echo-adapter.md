---
title: 步骤 3：实现 Echo 适配器的连接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc223901-3ad3-4e71-8672-fea6bb4efe65
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb452db2e3bd2728ff6b7e9fe5ba3879d3efc41e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363216"
---
# <a name="step-3-implement-the-connection-for-the-echo-adapter"></a><span data-ttu-id="f244b-102">步骤 3：实现 Echo 适配器的连接</span><span class="sxs-lookup"><span data-stu-id="f244b-102">Step 3: Implement the Connection for the Echo Adapter</span></span>
<span data-ttu-id="f244b-103">![第 3 部分，共 9 步](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span><span class="sxs-lookup"><span data-stu-id="f244b-103">![Step 3 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span></span>  

 <span data-ttu-id="f244b-104">**若要完成的时间：** 45 分钟</span><span class="sxs-lookup"><span data-stu-id="f244b-104">**Time to complete:** 45 minutes</span></span>  

 <span data-ttu-id="f244b-105">在此步骤中，将实现 Echo 适配器的连接功能。</span><span class="sxs-lookup"><span data-stu-id="f244b-105">In this step, you implement the connection capability of the Echo adapter.</span></span> <span data-ttu-id="f244b-106">根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，连接到目标系统时，必须实现以下抽象类和接口。</span><span class="sxs-lookup"><span data-stu-id="f244b-106">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], you must implement the following abstract class and interfaces when connecting to the target system.</span></span>  

- `Microsoft.ServiceModel.Channels.Common.ConnectionUri`  

- `Microsoft.ServiceModel.Channels.Common.IConnection`  

- `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`  

  <span data-ttu-id="f244b-107">而不是派生自上述抽象类和接口，[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成三个派生的类、 EchoAdapterConnection、 EchoAdapterConnectionUri 和 EchoAdapterConnectionFactory。</span><span class="sxs-lookup"><span data-stu-id="f244b-107">Instead of deriving from the above abstract class and interfaces, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the three derived classes, EchoAdapterConnection, EchoAdapterConnectionUri, and EchoAdapterConnectionFactory.</span></span> <span data-ttu-id="f244b-108">除了创建类，每个已引发特定异常的默认方法`System.NotImplementedException`。</span><span class="sxs-lookup"><span data-stu-id="f244b-108">In addition to creating the classes, each has a default method that throws a specific exception, `System.NotImplementedException`.</span></span>  <span data-ttu-id="f244b-109">此语句提醒开发人员可以实现的每个类。</span><span class="sxs-lookup"><span data-stu-id="f244b-109">This statement reminds the developer to implement each class.</span></span>  <span data-ttu-id="f244b-110">实现类时，必须删除此引发异常的语句。</span><span class="sxs-lookup"><span data-stu-id="f244b-110">When the class is implemented, this exception-throwing statement must be removed.</span></span>  

  <span data-ttu-id="f244b-111">在以下部分中，您将更新这些 3 个类来更好地理解如何处理连接、 URI 结构是什么，以及如何以编程方式检索各种 URI 元素，并使用该适配器中的这些元素。</span><span class="sxs-lookup"><span data-stu-id="f244b-111">In the following section, you update those three classes to get a better understanding of how to handle a connection, what the URI structure is, and how to programmatically retrieve various URI elements and then use those elements within the adapter.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="f244b-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="f244b-112">Prerequisites</span></span>  
 <span data-ttu-id="f244b-113">在开始此步骤之前，你必须已成功完成[步骤 2:将适配器和连接属性分类](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f244b-113">Before you begin this step, you must have successfully completed [Step 2: Categorize the Adapter and Connection Properties](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).</span></span> <span data-ttu-id="f244b-114">并且您应清楚地了解`Microsoft.ServiceModel.Channels.Common.IConnection`， `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`，和`Microsoft.ServiceModel.Channels.Common.ConnectionUri`类。</span><span class="sxs-lookup"><span data-stu-id="f244b-114">And you should have a clear understanding of the `Microsoft.ServiceModel.Channels.Common.IConnection`, `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`, and `Microsoft.ServiceModel.Channels.Common.ConnectionUri` classes.</span></span>  

## <a name="connection-related-classes"></a><span data-ttu-id="f244b-115">与连接相关的类</span><span class="sxs-lookup"><span data-stu-id="f244b-115">Connection-Related Classes</span></span>  
 <span data-ttu-id="f244b-116">[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]生成三个派生的类、 EchoAdapterConnection、 EchoAdapterConnectionUri 和 EchoAdapterConnectionFactory。</span><span class="sxs-lookup"><span data-stu-id="f244b-116">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] generates three derived classes, EchoAdapterConnection, EchoAdapterConnectionUri, and EchoAdapterConnectionFactory.</span></span> <span data-ttu-id="f244b-117">下面提供了与每个关联方法的简要概述。</span><span class="sxs-lookup"><span data-stu-id="f244b-117">The following provides a brief overview of methods associated with each.</span></span>  

### <a name="echoadapterconnection"></a><span data-ttu-id="f244b-118">EchoAdapterConnection</span><span class="sxs-lookup"><span data-stu-id="f244b-118">EchoAdapterConnection</span></span>  
 <span data-ttu-id="f244b-119">具体取决于适配器的复杂性，可能需要实现所有以下五种方法。</span><span class="sxs-lookup"><span data-stu-id="f244b-119">Depending on your adapter complexity, you might need to implement all of the following five methods.</span></span> <span data-ttu-id="f244b-120">对于 Echo 适配器，大多数都不支持的因为 Echo 适配器示例不涉及任何目标系统。</span><span class="sxs-lookup"><span data-stu-id="f244b-120">For Echo adapter, most are not supported, because the Echo adapter sample does not involve any target system.</span></span>  

|<span data-ttu-id="f244b-121">**方法**</span><span class="sxs-lookup"><span data-stu-id="f244b-121">**Method**</span></span>|<span data-ttu-id="f244b-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="f244b-122">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="f244b-123">public void 关闭 （TimeSpan 超时）</span><span class="sxs-lookup"><span data-stu-id="f244b-123">public void Close(TimeSpan timeout)</span></span>|<span data-ttu-id="f244b-124">关闭到目标系统的连接。</span><span class="sxs-lookup"><span data-stu-id="f244b-124">Closes the connection to the target system.</span></span> <span data-ttu-id="f244b-125">Echo 适配器使用此方法仅将跟踪事件添加到跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="f244b-125">The Echo adapter uses this method to only add trace events to the trace listener.</span></span>|  
|<span data-ttu-id="f244b-126">public bool IsValid(TimeSpan timeout)</span><span class="sxs-lookup"><span data-stu-id="f244b-126">public bool IsValid(TimeSpan timeout)</span></span>|<span data-ttu-id="f244b-127">返回一个值，该值指示连接是否仍有效。</span><span class="sxs-lookup"><span data-stu-id="f244b-127">Returns a value indicating whether the connection is still valid.</span></span><br /><br /> <span data-ttu-id="f244b-128">不支持 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="f244b-128">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="f244b-129">public void 打开 （TimeSpan 超时）</span><span class="sxs-lookup"><span data-stu-id="f244b-129">public void Open(TimeSpan timeout)</span></span>|<span data-ttu-id="f244b-130">将打开与目标系统的连接。</span><span class="sxs-lookup"><span data-stu-id="f244b-130">Opens the connection to the target system.</span></span><br /><br /> <span data-ttu-id="f244b-131">Echo 适配器的不适用。</span><span class="sxs-lookup"><span data-stu-id="f244b-131">N/A for the Echo adapter.</span></span> <span data-ttu-id="f244b-132">但是，该示例演示您如何使用名为 enableAuthentication URI 元素要求用户提供的用户名。</span><span class="sxs-lookup"><span data-stu-id="f244b-132">However, the example shows you how to use a URI element called enableAuthentication to require users to provide a user name.</span></span>|  
|<span data-ttu-id="f244b-133">public void ClearContext()</span><span class="sxs-lookup"><span data-stu-id="f244b-133">public void ClearContext()</span></span>|<span data-ttu-id="f244b-134">清除连接的上下文。</span><span class="sxs-lookup"><span data-stu-id="f244b-134">Clears the context of the connection.</span></span> <span data-ttu-id="f244b-135">当连接重新设置为连接池时，调用此方法。</span><span class="sxs-lookup"><span data-stu-id="f244b-135">This method is called when the connection is set back to the connection pool.</span></span><br /><br /> <span data-ttu-id="f244b-136">不支持 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="f244b-136">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="f244b-137">public void Abort()</span><span class="sxs-lookup"><span data-stu-id="f244b-137">public void Abort()</span></span>|<span data-ttu-id="f244b-138">中止连接到目标系统。</span><span class="sxs-lookup"><span data-stu-id="f244b-138">Aborts the connection to the target system.</span></span><br /><br /> <span data-ttu-id="f244b-139">不支持 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="f244b-139">Not supported by the Echo adapter.</span></span>|  

### <a name="echoadapterconnectionfactory"></a><span data-ttu-id="f244b-140">EchoAdapterConnectionFactory</span><span class="sxs-lookup"><span data-stu-id="f244b-140">EchoAdapterConnectionFactory</span></span>  
 <span data-ttu-id="f244b-141">连接工厂负责创建连接。</span><span class="sxs-lookup"><span data-stu-id="f244b-141">The connection factory is responsible for creating the connection.</span></span> <span data-ttu-id="f244b-142">默认情况下，您必须修改此类，仅当连接到目标系统时。</span><span class="sxs-lookup"><span data-stu-id="f244b-142">By default, you must modify this class only when connecting to a target system.</span></span> <span data-ttu-id="f244b-143">尽管 Echo 适配器不涉及任何目标系统，它显示了您如何使用名为 enableAuthentication，如果你的连接需要用户身份验证的自定义 URI 元素。</span><span class="sxs-lookup"><span data-stu-id="f244b-143">Although the Echo adapter does not involve any target system, it shows you how to use a custom URI element called enableAuthentication if your connection requires user authentication.</span></span>  

> [!NOTE]
>  <span data-ttu-id="f244b-144">EnableAuthentication 不是一个关键字，它是变量的名称。</span><span class="sxs-lookup"><span data-stu-id="f244b-144">The enableAuthentication is not a keyword, it is just a variable name.</span></span> <span data-ttu-id="f244b-145">因此，您可以选择为其任何名称。</span><span class="sxs-lookup"><span data-stu-id="f244b-145">Hence, you can choose any name for it.</span></span>  

### <a name="echoadapterconnectionuri"></a><span data-ttu-id="f244b-146">EchoAdapterConnectionUri</span><span class="sxs-lookup"><span data-stu-id="f244b-146">EchoAdapterConnectionUri</span></span>  
 <span data-ttu-id="f244b-147">这表示在目标系统的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="f244b-147">This represents a connection string to the target system.</span></span>  


|               <span data-ttu-id="f244b-148">**方法**</span><span class="sxs-lookup"><span data-stu-id="f244b-148">**Method**</span></span>               |                                                                                                                                       <span data-ttu-id="f244b-149">**说明**</span><span class="sxs-lookup"><span data-stu-id="f244b-149">**Description**</span></span>                                                                                                                                        |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        <span data-ttu-id="f244b-150">公共重写 Uri Uri</span><span class="sxs-lookup"><span data-stu-id="f244b-150">public override Uri Uri</span></span>         |                                                                                                    <span data-ttu-id="f244b-151">获取和设置的 Uri。</span><span class="sxs-lookup"><span data-stu-id="f244b-151">Gets and sets the Uri.</span></span> <span data-ttu-id="f244b-152">获取生成的 Uri 字符串并设置要分析的 Uri 字符串。</span><span class="sxs-lookup"><span data-stu-id="f244b-152">Gets to build the Uri string and sets to parse the Uri string.</span></span>                                                                                                     |
|   <span data-ttu-id="f244b-153">public EchoAdapterConnectionUri()</span><span class="sxs-lookup"><span data-stu-id="f244b-153">public EchoAdapterConnectionUri()</span></span>    |                                                                                                                    <span data-ttu-id="f244b-154">初始化 ConnectionUri 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="f244b-154">Initializes a new instance of the ConnectionUri class.</span></span>                                                                                                                    |
| <span data-ttu-id="f244b-155">公共重写字符串 SampleUriString</span><span class="sxs-lookup"><span data-stu-id="f244b-155">public override string SampleUriString</span></span> | <span data-ttu-id="f244b-156">返回 EchoAdapter.SCHEME +": //{hostname}/{application}?enableAuthentication={True&#124;False}"。</span><span class="sxs-lookup"><span data-stu-id="f244b-156">Returns EchoAdapter.SCHEME + "://{hostname}/{application}?enableAuthentication={True&#124;False}".</span></span><br /><br /> <span data-ttu-id="f244b-157">此返回的字符串将显示为**示例**中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，如下面的图中所示。</span><span class="sxs-lookup"><span data-stu-id="f244b-157">This return string displays as the **Example** in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, as shown in the following figure.</span></span> |

 <span data-ttu-id="f244b-158">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")</span><span class="sxs-lookup"><span data-stu-id="f244b-158">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")</span></span>  

## <a name="echo-adapter-connection-uri"></a><span data-ttu-id="f244b-159">Echo 适配器连接 URI</span><span class="sxs-lookup"><span data-stu-id="f244b-159">Echo Adapter Connection URI</span></span>  
 <span data-ttu-id="f244b-160">示例 Echo 适配器连接 URI 被描述为：EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true&#124;false}</span><span class="sxs-lookup"><span data-stu-id="f244b-160">The sample Echo adapter connection URI is described as: EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true&#124;false}</span></span>  

 <span data-ttu-id="f244b-161">由于 EchoAapter.SCHEME echov2，连接 URI 是指：</span><span class="sxs-lookup"><span data-stu-id="f244b-161">Since the EchoAapter.SCHEME is echov2, the connection URI is:</span></span>  

 <span data-ttu-id="f244b-162">echo2://lobhostname/lobapplication?enableAuthentication={true&#124;false}</span><span class="sxs-lookup"><span data-stu-id="f244b-162">echo2://lobhostname/lobapplication?enableAuthentication={true&#124;false}</span></span>  

 <span data-ttu-id="f244b-163">可以读取的上一个连接 URI 时 enableAuthentication = false，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f244b-163">You can read the previous connection URI when enableAuthentication=false as follows:</span></span>  

 <span data-ttu-id="f244b-164">使用 echov2 传输架构，转到一个名为 lobhostname，计算机名为 lobapplication 不需要任何身份验证的应用程序正在等待你的连接。</span><span class="sxs-lookup"><span data-stu-id="f244b-164">Using the echov2 transport schema, go to a computer named lobhostname, where an application named lobapplication that does not require any authentication is waiting for your connection.</span></span>  

 <span data-ttu-id="f244b-165">或者如果 enableAuthentication = true，读取连接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f244b-165">Or, when enableAuthentication=true, read the connection as follows:</span></span>  

 <span data-ttu-id="f244b-166">使用 echov2 传输架构，转到一个名为 lobhostname，计算机名为 lobapplication 的应用程序需要身份验证正在等待你的连接。</span><span class="sxs-lookup"><span data-stu-id="f244b-166">Using the echov2 transport schema, go to a computer named lobhostname, where an application named lobapplication expects that authentication is waiting for your connection.</span></span> <span data-ttu-id="f244b-167">Echo 适配器仅用户名称是必需的。</span><span class="sxs-lookup"><span data-stu-id="f244b-167">For the Echo adapter, only a user name is required.</span></span>  

 <span data-ttu-id="f244b-168">使用定义的 URI，可以以编程方式使用并对其进行分析的连接和配置。</span><span class="sxs-lookup"><span data-stu-id="f244b-168">With a defined URI, you can programmatically consume and parse it for connectivity and configuration.</span></span> <span data-ttu-id="f244b-169">如果连接需要用户名和密码等敏感数据，不包含在 URI 中的此类信息。</span><span class="sxs-lookup"><span data-stu-id="f244b-169">If the connection requires sensitive data such as a user name and password, do not contain such information in the URI.</span></span> <span data-ttu-id="f244b-170">相反，请添加此类信息中的`System.ServiceModel.Description.ClientCredentials`对象。</span><span class="sxs-lookup"><span data-stu-id="f244b-170">Instead, add such information in the `System.ServiceModel.Description.ClientCredentials` object.</span></span> <span data-ttu-id="f244b-171">您添加的代码示例演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f244b-171">The code example that you add shows you how to do so.</span></span>  

 <span data-ttu-id="f244b-172">在下面的代码，Echo 适配器构造以两种方式向您展示适配器如何使用各种 URI 元素修改适配器功能的 URI。</span><span class="sxs-lookup"><span data-stu-id="f244b-172">In the following code, the Echo adapter constructs the URI in two ways to show you how the adapter can use various URI elements to modify the adapter feature.</span></span>  

 <span data-ttu-id="f244b-173">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]</span><span class="sxs-lookup"><span data-stu-id="f244b-173">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]</span></span>  

 <span data-ttu-id="f244b-174">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]&echoInUpperCase=true</span><span class="sxs-lookup"><span data-stu-id="f244b-174">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]&echoInUpperCase=true</span></span>  

### <a name="retrieving-the-uri-element"></a><span data-ttu-id="f244b-175">检索 URI 元素</span><span class="sxs-lookup"><span data-stu-id="f244b-175">Retrieving the URI Element</span></span>  
 <span data-ttu-id="f244b-176">可以分析在 Echo 适配器 URI echo2 中的每个 URI 元素: / lobhostname/lobapplication？ enableAuthentication = false 和 echoInUpperCase = false。</span><span class="sxs-lookup"><span data-stu-id="f244b-176">You can parse each URI element in the Echo adapter URI echo2://lobhostname/lobapplication?enableAuthentication=false&echoInUpperCase=false.</span></span>  <span data-ttu-id="f244b-177">下表中列出了 URI 的元素值和关联的方法：</span><span class="sxs-lookup"><span data-stu-id="f244b-177">The URI element values and associated methods are listed in the following table:</span></span>  

|<span data-ttu-id="f244b-178">**URI 元素值**</span><span class="sxs-lookup"><span data-stu-id="f244b-178">**URI Element Value**</span></span>|<span data-ttu-id="f244b-179">**方法**</span><span class="sxs-lookup"><span data-stu-id="f244b-179">**Method**</span></span>|  
|---------------------------|----------------|  
|<span data-ttu-id="f244b-180">lobhostname</span><span class="sxs-lookup"><span data-stu-id="f244b-180">lobhostname</span></span>|<span data-ttu-id="f244b-181">`System.Uri.Host%2A` 若要检索主机名</span><span class="sxs-lookup"><span data-stu-id="f244b-181">`System.Uri.Host%2A` to retrieve the host name</span></span>|  
|<span data-ttu-id="f244b-182">Lobapplication</span><span class="sxs-lookup"><span data-stu-id="f244b-182">Lobapplication</span></span>|<span data-ttu-id="f244b-183">`System.Uri.AbsolutePath%2A` 若要检索目标应用程序名称</span><span class="sxs-lookup"><span data-stu-id="f244b-183">`System.Uri.AbsolutePath%2A` to retrieve the target application name</span></span>|  
|<span data-ttu-id="f244b-184">enableAuthentation=false</span><span class="sxs-lookup"><span data-stu-id="f244b-184">enableAuthentation=false</span></span>|<span data-ttu-id="f244b-185">GetQueryStringValue("enableAuthentication")</span><span class="sxs-lookup"><span data-stu-id="f244b-185">GetQueryStringValue("enableAuthentication")</span></span><br /><br /> <span data-ttu-id="f244b-186">使用此 URI 元素来验证用户凭据**注意：** GetQueryStringValue 是中定义的静态方法 `Microsoft.ServiceModel.Channels.Common.ConnectionUri`</span><span class="sxs-lookup"><span data-stu-id="f244b-186">Use this URI element to validate user credentials **Note:**  GetQueryStringValue is a static method defined in the `Microsoft.ServiceModel.Channels.Common.ConnectionUri`</span></span>|  
|<span data-ttu-id="f244b-187">echoInUpperValue=false</span><span class="sxs-lookup"><span data-stu-id="f244b-187">echoInUpperValue=false</span></span>|<span data-ttu-id="f244b-188">GetQueryStringValue("echoInUpperValue")</span><span class="sxs-lookup"><span data-stu-id="f244b-188">GetQueryStringValue("echoInUpperValue")</span></span><br /><br /> <span data-ttu-id="f244b-189">使用此 URI 元素将传入的字符串转换为大写。</span><span class="sxs-lookup"><span data-stu-id="f244b-189">Use this URI element to convert the incoming string to upper case.</span></span>|  

### <a name="enableauthentication-uri-element"></a><span data-ttu-id="f244b-190">EnableAuthentication URI 元素</span><span class="sxs-lookup"><span data-stu-id="f244b-190">EnableAuthentication URI Element</span></span>  
 <span data-ttu-id="f244b-191">目标系统通常要求提供客户端凭据以建立与目标系统的连接。</span><span class="sxs-lookup"><span data-stu-id="f244b-191">Your target system often requires you to provide client credentials to establish a connection to the target system.</span></span> <span data-ttu-id="f244b-192">如前文所述，Echo 适配器不涉及任何目标系统。</span><span class="sxs-lookup"><span data-stu-id="f244b-192">As mentioned, the Echo adapter does not involve any target system.</span></span> <span data-ttu-id="f244b-193">作为一个示例，但它演示如何使用名为 enableAuthentication 的自定义 URI 元素提供的凭据。</span><span class="sxs-lookup"><span data-stu-id="f244b-193">Though as a sample, it shows how to use a custom URI element called enableAuthentication to provide the credentials.</span></span>  

```  
 public class EchoAdapterConnection : IConnection   
{  
….  
   public void Open(TimeSpan timeout)  
  {  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
  }  
}  
```  

 <span data-ttu-id="f244b-194">代码检查以查看是否 enableAuthentication 为 true，如果未提供的用户名;如果未提供用户名，则会引发异常，它由捕获[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f244b-194">The code checks to see if enableAuthentication is true and if a user name is not provided; if a user name is not provided, it throws an exception, which is caught by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, as shown below:</span></span>  

 <span data-ttu-id="f244b-195">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")</span><span class="sxs-lookup"><span data-stu-id="f244b-195">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")</span></span>  

 <span data-ttu-id="f244b-196">若要提供的用户名，则可以输入它在配置适配器对话框中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，如下面的图中所示：</span><span class="sxs-lookup"><span data-stu-id="f244b-196">To provide the user name, you can enter it in the Configure Adapter dialog box in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, as shown in the following figure:</span></span>  

 <span data-ttu-id="f244b-197">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")</span><span class="sxs-lookup"><span data-stu-id="f244b-197">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")</span></span>  

### <a name="echoinuppercase-uri-element"></a><span data-ttu-id="f244b-198">EchoInUpperCase URI 元素</span><span class="sxs-lookup"><span data-stu-id="f244b-198">EchoInUpperCase URI Element</span></span>  
 <span data-ttu-id="f244b-199">布尔标志，例如，可以引用 EchoInUpperCase URI 元素。</span><span class="sxs-lookup"><span data-stu-id="f244b-199">The EchoInUpperCase URI element can be referenced like a Boolean flag.</span></span> <span data-ttu-id="f244b-200">如果标志为 true，则适配器会将 EchoStrings 操作的输入的字符串转换为大写。</span><span class="sxs-lookup"><span data-stu-id="f244b-200">If the flag is true, then the adapter converts the input string of the EchoStrings operation to uppercase.</span></span>  

 <span data-ttu-id="f244b-201">若要更改 echoInUpperCase URI 元素的默认值，请使用 URI 属性选项卡中的配置适配器[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f244b-201">To change the default value of the echoInUpperCase URI element, use the URI Properties tab of the Configure Adapter in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], as shown below.</span></span>  

 <span data-ttu-id="f244b-202">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")</span><span class="sxs-lookup"><span data-stu-id="f244b-202">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")</span></span>  

## <a name="updating-echoadapterconnection"></a><span data-ttu-id="f244b-203">正在更新 EchoAdapterConnection</span><span class="sxs-lookup"><span data-stu-id="f244b-203">Updating EchoAdapterConnection</span></span>  
 <span data-ttu-id="f244b-204">实现 EchoAdapterConnection 类的 IsValid、 打开和关闭方法。</span><span class="sxs-lookup"><span data-stu-id="f244b-204">You implement the IsValid, Open, and Close method of the EchoAdapterConnection class.</span></span>  

#### <a name="to-update-the-echoadapterconnection-class"></a><span data-ttu-id="f244b-205">若要更新 EchoAdapterConnection 类</span><span class="sxs-lookup"><span data-stu-id="f244b-205">To update the EchoAdapterConnection class</span></span>  

1.  <span data-ttu-id="f244b-206">在中**解决方案资源管理器**，双击**EchoAdapterConnection.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="f244b-206">In **Solution Explorer**, double-click the **EchoAdapterConnection.cs** file.</span></span>  

2.  <span data-ttu-id="f244b-207">在 Visual Studio 编辑器中，右键单击任意位置在编辑器内，在上下文菜单中，指向**大纲**，然后单击**停止大纲显示**。</span><span class="sxs-lookup"><span data-stu-id="f244b-207">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  

3.  <span data-ttu-id="f244b-208">在 Visual Studio 编辑器中，找到**IsValid**方法。</span><span class="sxs-lookup"><span data-stu-id="f244b-208">In the Visual Studio editor, find the **IsValid** method.</span></span> <span data-ttu-id="f244b-209">内部**IsValid**方法中，现有实现替换为如下：</span><span class="sxs-lookup"><span data-stu-id="f244b-209">Inside the **IsValid** method, replace the existing implementation with the one below:</span></span>  

    ```csharp  
    return true;  
    ```  

4.  <span data-ttu-id="f244b-210">在 Visual Studio 编辑器中，找到**打开**方法。</span><span class="sxs-lookup"><span data-stu-id="f244b-210">In the Visual Studio editor, find the **Open** method.</span></span> <span data-ttu-id="f244b-211">内部**打开**方法中，现有实现替换为以下实现。</span><span class="sxs-lookup"><span data-stu-id="f244b-211">Inside the **Open** method, replace the existing implementation with the following implementation.</span></span> <span data-ttu-id="f244b-212">这显示了如何使用 URI enableAuthentication 元素以确保提供的用户名：</span><span class="sxs-lookup"><span data-stu-id="f244b-212">This shows you how to use the URI enableAuthentication element to ensure user  name is provided:</span></span>  

    ```csharp  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        // it just logs the credentials in the trace file  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
        // got the username, log it in trace file  
        EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Username is " + this.connectionFactory.ClientCredentials.UserName.UserName);  
    }  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully established!");  
    ```  

5.  <span data-ttu-id="f244b-213">在 Visual Studio 编辑器中，找到**关闭**方法。</span><span class="sxs-lookup"><span data-stu-id="f244b-213">In the Visual Studio editor, find the **Close** method.</span></span> <span data-ttu-id="f244b-214">内部**关闭**方法中，添加下面的单个语句：</span><span class="sxs-lookup"><span data-stu-id="f244b-214">Inside the **Close** method, add the following single statement:</span></span>  

    ```csharp  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Close", "Connection successfully closed!");  
    ```  

## <a name="updating-the-echoadapterconnectionfactory"></a><span data-ttu-id="f244b-215">正在更新 EchoAdapterConnectionFactory</span><span class="sxs-lookup"><span data-stu-id="f244b-215">Updating the EchoAdapterConnectionFactory</span></span>  
 <span data-ttu-id="f244b-216">实现 EchoAdapterConnectionFactory 构造函数，并添加名为 ClientCredentials 和 ConnectionUri 的两个属性。</span><span class="sxs-lookup"><span data-stu-id="f244b-216">You implement EchoAdapterConnectionFactory constructor, and add two properties called ClientCredentials and ConnectionUri.</span></span>  

#### <a name="to-update-the-echoadapterconnectionfactory-class"></a><span data-ttu-id="f244b-217">若要更新 EchoAdapterConnectionFactory 类</span><span class="sxs-lookup"><span data-stu-id="f244b-217">To update the EchoAdapterConnectionFactory class</span></span>  

1.  <span data-ttu-id="f244b-218">在中**解决方案资源管理器**，双击**EchoAdapterConnectionFactory.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="f244b-218">In **Solution Explorer**, double-click the **EchoAdapterConnectionFactory.cs** file.</span></span>  

2.  <span data-ttu-id="f244b-219">在 Visual Studio 编辑器中，右键单击任意位置在编辑器内，在上下文菜单中，指向**大纲**，然后单击**停止大纲显示**。</span><span class="sxs-lookup"><span data-stu-id="f244b-219">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  

3.  <span data-ttu-id="f244b-220">在 Visual Studio 编辑器中，找到**私有字段**区域。</span><span class="sxs-lookup"><span data-stu-id="f244b-220">In the Visual Studio editor, find the **Private Fields** region.</span></span> <span data-ttu-id="f244b-221">添加下面的单个语句：</span><span class="sxs-lookup"><span data-stu-id="f244b-221">Add the following single statement:</span></span>  

    ```csharp  
    private EchoAdapterConnectionUri connectionUri;  
    ```  

     <span data-ttu-id="f244b-222">列表的私有字段应匹配以下项：</span><span class="sxs-lookup"><span data-stu-id="f244b-222">Your list of private fields should match the following:</span></span>  

    ```csharp  
    // Stores the client credentials  
    private ClientCredentials clientCredentials;  
    // Stores the adapter class  
    private EchoAdapter adapter;  
    private EchoAdapterConnectionUri connectionUri;  
    ```  

4.  <span data-ttu-id="f244b-223">在 Visual Studio 编辑器中，找到**EchoAdapterConnectionFactory**方法。</span><span class="sxs-lookup"><span data-stu-id="f244b-223">In the Visual Studio editor, find the **EchoAdapterConnectionFactory** method.</span></span> <span data-ttu-id="f244b-224">内部**EchoAdapterConnectionFactory**构造函数方法之前"}"，添加下面的单个语句作为最后一条语句。</span><span class="sxs-lookup"><span data-stu-id="f244b-224">Inside the **EchoAdapterConnectionFactory** constructor method, before "}", add the following single statement as the last statement.</span></span>  

    ```csharp  
    this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    ```  

     <span data-ttu-id="f244b-225">实现**EchoAdapterConnectionFactory**方法应匹配以下内容：</span><span class="sxs-lookup"><span data-stu-id="f244b-225">The implementation of the **EchoAdapterConnectionFactory** method should match the following:</span></span>  

    ```csharp  
    /// <summary>  
    /// Initializes a new instance of the EchoAdapterConnectionFactory class  
    /// </summary>  
    public EchoAdapterConnectionFactory(ConnectionUri connectionUri  
        , ClientCredentials clientCredentials  
        , EchoAdapter adapter)  
    {  
        this.clientCredentials = clientCredentials;  
        this.adapter = adapter;  
        //added  
        this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    }  
    ```  

5.  <span data-ttu-id="f244b-226">在 Visual Studio 编辑器中，找到**公共属性**区域。</span><span class="sxs-lookup"><span data-stu-id="f244b-226">In the Visual Studio editor, find the **Public Properties** region.</span></span> <span data-ttu-id="f244b-227">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="f244b-227">Add the following code:</span></span>  

    ```csharp  
    /// <summary>  
    /// Returns the client credentials  
    /// </summary>  
    public ClientCredentials ClientCredentials  
    {  
        get  
        {  
            return this.clientCredentials;  
        }  
    }  

    /// <summary>  
    /// Returns the Connection Uri for this adapter  
    /// </summary>  
    public EchoAdapterConnectionUri ConnectionUri  
    {  
        get  
        {  
            return this.connectionUri;  
        }  
    }  
    ```  

## <a name="updating-the-echoadapterconnectionuri"></a><span data-ttu-id="f244b-228">正在更新 EchoAdapterConnectionUri</span><span class="sxs-lookup"><span data-stu-id="f244b-228">Updating the EchoAdapterConnectionUri</span></span>  
 <span data-ttu-id="f244b-229">实现 EchoAdapterConnectionUri 默认构造函数、 EchoAdapterConnectionUri(Uri uri) 重载构造函数，并且公共重写 Uri Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="f244b-229">You implement the EchoAdapterConnectionUri default constructor, EchoAdapterConnectionUri(Uri uri) overloaded constructor, and the public override Uri Uri property.</span></span>  

#### <a name="to-update-the-echoadapterconnectionuri-class"></a><span data-ttu-id="f244b-230">若要更新 EchoAdapterConnectionUri 类</span><span class="sxs-lookup"><span data-stu-id="f244b-230">To update the EchoAdapterConnectionUri class</span></span>  

1.  <span data-ttu-id="f244b-231">在中**解决方案资源管理器**，双击**EchoAdapterConnectionUri.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="f244b-231">In **Solution Explorer**, double-click the **EchoAdapterConnectionUri.cs** file.</span></span>  

2.  <span data-ttu-id="f244b-232">在 Visual Studio 编辑器中，右键单击任意位置在编辑器内，在上下文菜单中，指向**大纲**，然后单击**停止大纲显示**。</span><span class="sxs-lookup"><span data-stu-id="f244b-232">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  

3.  <span data-ttu-id="f244b-233">在 Visual Studio 编辑器中，找到**构造函数**区域。</span><span class="sxs-lookup"><span data-stu-id="f244b-233">In the Visual Studio editor, find the **Constructors** region.</span></span> <span data-ttu-id="f244b-234">内部**EchoAdapterConnectionUri()** 默认构造函数中，添加以下语句：</span><span class="sxs-lookup"><span data-stu-id="f244b-234">Inside the **EchoAdapterConnectionUri()** default constructor, add the following statement:</span></span>  

    ```csharp  
    Uri = new Uri("echov2://lobhostname/lobapplication?enableauthentication=False");  
    ```  

4.  <span data-ttu-id="f244b-235">在 Visual Studio 编辑器中，内部**EchoAdapterConnectionUri (Uri uri)** 重载构造函数，并添加以下语句：</span><span class="sxs-lookup"><span data-stu-id="f244b-235">In the Visual Studio editor, inside the **EchoAdapterConnectionUri(Uri uri)** overloaded constructor, and add the following statement:</span></span>  

    ```csharp  
    Uri = uri;  
    ```  

     <span data-ttu-id="f244b-236">EchoAdapterConnectionUri(Uri uri) 方法的实现应匹配以下项：</span><span class="sxs-lookup"><span data-stu-id="f244b-236">Your implementation of the EchoAdapterConnectionUri(Uri uri) method should match the following:</span></span>  

    ```csharp  
    public EchoAdapterConnectionUri(Uri uri)  
        : base()  
    {  
        Uri = uri;  
    }  
    ```  

5.  <span data-ttu-id="f244b-237">在 Visual Studio 编辑器中，内部**公共重写 Uri Uri**方法中，替换现有具有以下逻辑。</span><span class="sxs-lookup"><span data-stu-id="f244b-237">In the Visual Studio editor, inside the **public override Uri Uri** method, replace the existing with the following logic.</span></span> <span data-ttu-id="f244b-238">获取生成 echoInUpperCase 带或不带它的 Uri。</span><span class="sxs-lookup"><span data-stu-id="f244b-238">The get builds the Uri with echoInUpperCase or without it.</span></span> <span data-ttu-id="f244b-239">设置分析的 URI 来检索主机名、 数据库名称和查询值。</span><span class="sxs-lookup"><span data-stu-id="f244b-239">The set parses the URI to retrieve host name, database name, and query values.</span></span>  

    ```csharp  
    get  
    {  
        // Build the uri  
        if (String.IsNullOrEmpty(this.hostname)) throw new InvalidUriException("Invalid target system host name.");  
        if (String.IsNullOrEmpty(this.application)) throw new InvalidUriException("Invalid target system data source name.");  
        if (EchoInUpperCase)  
        {  
            // build the uri with echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication + "&" + "echoInUpperCase=" + echoInUpperCase);  
        }  
        else  
        {  
            // build the uri without echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication);  
        }  
    }  
    set  
    {  
        // Parse the uri  
        String[] enableAuthValue = GetQueryStringValue(value, "enableAuthentication");  
        if (enableAuthValue.Length > 0) this.enableAuthentication = Boolean.Parse(enableAuthValue[0]);  
        String[] echoInUpperValue = GetQueryStringValue(value, "echoInUpperCase");  
        if (echoInUpperValue.Length > 0) this.echoInUpperCase = Boolean.Parse(echoInUpperValue[0]);  

        this.hostname = value.Host;  
        String[] applicationValue = value.AbsolutePath.Split('/');  
        if (applicationValue.Length > 1) this.Application = applicationValue[1];  
    }  
    ```  

6.  <span data-ttu-id="f244b-240">在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="f244b-240">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  

7.  <span data-ttu-id="f244b-241">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="f244b-241">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="f244b-242">您应该已成功编译项目。</span><span class="sxs-lookup"><span data-stu-id="f244b-242">You should successfully compile the project.</span></span> <span data-ttu-id="f244b-243">如果没有，请确保您已按照上述每个步骤。</span><span class="sxs-lookup"><span data-stu-id="f244b-243">If not, ensure that you have followed every step above.</span></span>  

> [!NOTE]
>  <span data-ttu-id="f244b-244">保存所做的工作。</span><span class="sxs-lookup"><span data-stu-id="f244b-244">You saved your work.</span></span> <span data-ttu-id="f244b-245">可以安全地关闭 Visual Studio 或转到下一步，[步骤 4:实现 Echo 适配器的元数据浏览处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f244b-245">You can safely close Visual Studio at this time or go to the next step, [Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).</span></span>  

## <a name="what-did-i-just-do"></a><span data-ttu-id="f244b-246">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="f244b-246">What Did I Just Do?</span></span>  
 <span data-ttu-id="f244b-247">实现 Echo 适配器的连接。</span><span class="sxs-lookup"><span data-stu-id="f244b-247">You implemented the connection for the Echo adapter.</span></span> <span data-ttu-id="f244b-248">您学习了的连接组件[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、 连接 URI 的基本结构、 如何以编程方式分析 URI 元素，以及如何使用 URI 元素，若要更改适配器功能。</span><span class="sxs-lookup"><span data-stu-id="f244b-248">You learned the connection components of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the basic structure of the connection URI, how to programmatically parse the URI elements, and how you can use the URI element to change the adapter feature.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="f244b-249">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f244b-249">Next Steps</span></span>  
 <span data-ttu-id="f244b-250">您实现元数据浏览、 搜索和解析功能和出站消息交换。</span><span class="sxs-lookup"><span data-stu-id="f244b-250">You implement metadata browsing, searching, and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="f244b-251">最后，您生成并部署该适配器。</span><span class="sxs-lookup"><span data-stu-id="f244b-251">Finally, you build and deploy the adapter.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f244b-252">请参阅</span><span class="sxs-lookup"><span data-stu-id="f244b-252">See Also</span></span>  
 <span data-ttu-id="f244b-253">[步骤 4：实现 Echo 适配器的元数据浏览处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f244b-253">[Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="f244b-254">教程 1:开发 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="f244b-254">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)