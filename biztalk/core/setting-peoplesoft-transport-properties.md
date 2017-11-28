---
title: "设置 PeopleSoft 传输属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting transport properties
- transport properties, setting
ms.assetid: 44b5f015-59f1-43a3-9673-a5ba40266843
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ecfd221d28312e84dcbaf7d8c83abc4f5191f54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-peoplesoft-transport-properties"></a><span data-ttu-id="a2f4c-102">设置 PeopleSoft 传输属性</span><span class="sxs-lookup"><span data-stu-id="a2f4c-102">Setting PeopleSoft Transport Properties</span></span>
<span data-ttu-id="a2f4c-103">PeopleSoft 传输属性用于运行时和设计时。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-103">The PeopleSoft transport properties are used for design and run time.</span></span> <span data-ttu-id="a2f4c-104">在**传输属性**对话框中，你设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-104">In the **Transport Properties** dialog box, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="a2f4c-105">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="a2f4c-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="a2f4c-106">展开“适配器必需属性”，然后填写连接到 PeopleSoft 服务器所需的各项信息。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-106">Expand the Adapter Required Properties and fill in all required information for connection to the PeopleSoft server.</span></span>  
  
     <span data-ttu-id="a2f4c-107">必须设置配置参数才能将适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器连接到 PeopleSoft Enterprise。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-107">You must set configuration parameters to connect Microsoft BizTalk Adapter for PeopleSoft Enterprise to PeopleSoft Enterprise.</span></span> <span data-ttu-id="a2f4c-108">此数据是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-108">This data is case sensitive.</span></span>  
  
    |<span data-ttu-id="a2f4c-109">参数</span><span class="sxs-lookup"><span data-stu-id="a2f4c-109">Parameter</span></span>|<span data-ttu-id="a2f4c-110">Description</span><span class="sxs-lookup"><span data-stu-id="a2f4c-110">Description</span></span>|  
    |---------------|-----------------|  
    |`Application Server Path`|<span data-ttu-id="a2f4c-111">此字符串代表 PeopleSoft 应用程序服务器运行的计算机和侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-111">A string representing the computer and port on which the PeopleSoft Application Server is running and listening.</span></span> <span data-ttu-id="a2f4c-112">PeopleSoft 8 应用程序的 URL 路径的语法是 / / < 计算机名 >:\<端口 >。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-112">The syntax of the URL path to the PeopleSoft 8 Application is //<computer_name>:\<port>.</span></span> <span data-ttu-id="a2f4c-113">向你 PeopleSoft 管理员请求\<端口 > 值。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-113">Ask your PeopleSoft administrator for the \<port> value.</span></span> <span data-ttu-id="a2f4c-114">\<端口 > 值是震动协议侦听器端口，不是应用程序服务器端口。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-114">The \<port> value is the JOLT protocol listener port, not the App Server port.</span></span> <span data-ttu-id="a2f4c-115">默认 JOLT 端口为 9000。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-115">The default JOLT port is 9000.</span></span>|  
    |`JAVA_HOME`|<span data-ttu-id="a2f4c-116">设置 JAVA_HOME 变量以指向你 JDK 的安装，例如： **C:\j2sdk1.4.2_08**。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-116">Set the JAVA_HOME variable to point to your JDK installation, for example: **C:\j2sdk1.4.2_08**.</span></span>|  
    |`Password`|<span data-ttu-id="a2f4c-117">如果你未选择**使用 SSO**，必须设置为 BizTalk 适配器 PeopleSoft 企业访问服务器系统的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-117">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="a2f4c-118">表示用户密码的字符串，用于登录到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-118">A string representing the user's password for logon to a PeopleSoft system.</span></span> <span data-ttu-id="a2f4c-119">不会显示密码中的字符，而是以星号 (*) 表示这些字符。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-119">The characters do not appear but are represented by asterisks (*).</span></span>|  
    |`PeopleSoft 8.x Jar Files`|<span data-ttu-id="a2f4c-120">若要使用组件接口（仅限 PeopleSoft 8），则必须更新 CLASSPATH 以包含 PeopleSoft 组件接口 jar 文件。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-120">To use Ccmponent interfaces (PeopleSoft 8 only) you must update your CLASSPATH to include the PeopleSoft Component Interface jar file.</span></span> <span data-ttu-id="a2f4c-121">例如： **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-121">For example: **<PeopleSoft_Home>\web\PSJOA\psjoa.jar**.</span></span>|  
    |`User Name`|<span data-ttu-id="a2f4c-122">如果你未选择**使用 SSO**，必须设置为 BizTalk 适配器 PeopleSoft 企业访问服务器系统的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-122">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="a2f4c-123">表示用户名的字符串，用于登录到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-123">A string representing a user name required for logon to a PeopleSoft system.</span></span>|  
  
2.  <span data-ttu-id="a2f4c-124">输入**其他参数**时日期用作键的值; 它具有不同的格式。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-124">Enter an **Additional parameters** value when a date is used as a key; it has a different format.</span></span> <span data-ttu-id="a2f4c-125">YYYY-月-日是默认格式。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-125">YYYY-MM-DD is the default format.</span></span>  
  
3.  <span data-ttu-id="a2f4c-126">输入**并发控制**值在表示的调用，例如 200、 数**最大并发调用**如有必要。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-126">Enter a **Concurrency control** value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="a2f4c-127">**最大并发调用**参数激活过载保护，如果后端服务器无法处理的数据量。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-127">The **Max Concurrent Calls** parameter activates an overload protection if the back-end server cannot process the amount of data.</span></span> <span data-ttu-id="a2f4c-128">并行调用是适配器尚未进行回复的请求。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-128">A concurrent call is a request for which the adapter does not yet have a reply.</span></span> <span data-ttu-id="a2f4c-129">设置**最大并发调用**其中吞吐量超过后端处理功能的实例中。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-129">Set **Max Concurrent Calls** in instances where the throughput exceeds back-end processing capabilities.</span></span>  
  
     <span data-ttu-id="a2f4c-130">此字段的默认值为 -1，意味着未进行任何保护。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-130">The default value for this field is -1, meaning no protection occurs.</span></span>  
  
     <span data-ttu-id="a2f4c-131">如果 BizTalk Server 将请求提交到传输适配器，并且调用等于或超过为设置的值的并发数**最大并发调用**，提交请求被保存，直到并发调用数量的线程为降低到低于设置的值。</span><span class="sxs-lookup"><span data-stu-id="a2f4c-131">If BizTalk Server submits a request to the Transmit adapter, and the number of concurrent calls equals or exceeds the value set for **Max Concurrent Calls**, the thread submitting the request is saved until the concurrent calls number decreases to below the set value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f4c-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2f4c-132">See Also</span></span>  
 [<span data-ttu-id="a2f4c-133">创建 PeopleSoft 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="a2f4c-133">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)