---
title: "从 machine.config 中获取绑定扩展时出错 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65ab48cf-575b-4db6-984a-880f7e286959
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbe53def02f42c59cf5e40380c898f47695c19da
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error-getting-binding-extensions-from-machineconfig"></a><span data-ttu-id="e394c-102">从 machine.config 获取绑定扩展时出错。</span><span class="sxs-lookup"><span data-stu-id="e394c-102">Error getting binding extensions from machine.config</span></span>
## <a name="details"></a><span data-ttu-id="e394c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e394c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e394c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e394c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e394c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e394c-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="e394c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e394c-106">Event ID</span></span>|<span data-ttu-id="e394c-107">0</span><span class="sxs-lookup"><span data-stu-id="e394c-107">0</span></span>|  
|<span data-ttu-id="e394c-108">事件源</span><span class="sxs-lookup"><span data-stu-id="e394c-108">Event Source</span></span>|<span data-ttu-id="e394c-109">0</span><span class="sxs-lookup"><span data-stu-id="e394c-109">0</span></span>|  
|<span data-ttu-id="e394c-110">组件</span><span class="sxs-lookup"><span data-stu-id="e394c-110">Component</span></span>|<span data-ttu-id="e394c-111">0</span><span class="sxs-lookup"><span data-stu-id="e394c-111">0</span></span>|  
|<span data-ttu-id="e394c-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="e394c-112">Symbolic Name</span></span>|<span data-ttu-id="e394c-113">0</span><span class="sxs-lookup"><span data-stu-id="e394c-113">0</span></span>|  
|<span data-ttu-id="e394c-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="e394c-114">Message Text</span></span>|<span data-ttu-id="e394c-115">从 machine.config 获取绑定扩展时出错。</span><span class="sxs-lookup"><span data-stu-id="e394c-115">Error getting binding extensions from machine.config</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e394c-116">解释</span><span class="sxs-lookup"><span data-stu-id="e394c-116">Explanation</span></span>  
 <span data-ttu-id="e394c-117">当接收位置或发送端口绑定配置具有用户定义的绑定扩展，但 machine.config 文件中未定义该扩展时，发生此错误。</span><span class="sxs-lookup"><span data-stu-id="e394c-117">This error occurs when a  receive location or send port binding configuration has a user defined binding extension, but it is not defined in machine.config file.</span></span> <span data-ttu-id="e394c-118">这种情况主要会出现的 WCF 自定义和 WCF CustomIsolated 适配器。</span><span class="sxs-lookup"><span data-stu-id="e394c-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e394c-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="e394c-119">User Action</span></span>  
 <span data-ttu-id="e394c-120">在 machine.config 文件中定义接收位置或发送端口中使用的绑定扩展。</span><span class="sxs-lookup"><span data-stu-id="e394c-120">Define the binding extension used in the receive location or send port in machine.config file.</span></span> <span data-ttu-id="e394c-121">同时，要获取自定义行为或绑定元素以使用 WCF-Custom 适配器，请完成这些步骤：</span><span class="sxs-lookup"><span data-stu-id="e394c-121">Also, to get a custom behavior or binding element to work with WCF-Custom adapter, complete these steps:</span></span>  
  
1.  <span data-ttu-id="e394c-122">GAC 程序集</span><span class="sxs-lookup"><span data-stu-id="e394c-122">GAC the assembly</span></span>  
  
2.  <span data-ttu-id="e394c-123">修改 machine.config 文件 (位于**%FrameworkDir%\v4.0.30319\CONFIG**)。</span><span class="sxs-lookup"><span data-stu-id="e394c-123">Modify your machine.config file (found in **%FrameworkDir%\v4.0.30319\CONFIG**).</span></span>  
  
    1.  <span data-ttu-id="e394c-124">加载你的行为 DLL 在服务配置编辑器 (**svcConfigEditor.exe**)。</span><span class="sxs-lookup"><span data-stu-id="e394c-124">Load your behavior DLL inside the Service Configuration Editor (**svcConfigEditor.exe**).</span></span>  
  
    2.  <span data-ttu-id="e394c-125">保存到配置**app.config**文件</span><span class="sxs-lookup"><span data-stu-id="e394c-125">Save the configuration to an **app.config** file</span></span>  
  
    3.  <span data-ttu-id="e394c-126">复制并粘贴**system.servicemodel** machine.config 中的类似节中的扩展部分。如果**system.servicemodel**部分不在 machine.config，你必须创建一个。</span><span class="sxs-lookup"><span data-stu-id="e394c-126">Copy and paste the **system.servicemodel** extensions section in a similar section in machine.config. If **system.servicemodel** section is not present in machine.config, your must create one.</span></span> <span data-ttu-id="e394c-127">以下是 machine.config 文件的配置部分的示例：</span><span class="sxs-lookup"><span data-stu-id="e394c-127">The following is an example from the configuration section of a machine.config file:</span></span>  
  
        ```  
          <system.serviceModel>  
            <extensions>  
              <behaviorExtensions>  
                <add name="BizTalkWcfContractNamespaceTestServiceBehaviorExtension" type="ASB.BizTalk.Samples.BizTalkWcfContractNamespaceTestServiceBehaviorExtension, CustomBizTalkWcfBehaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=7631521c07cf34b4" />  
              </behaviorExtensions>  
            </extensions>  
          </system.serviceModel>  
        ```  
  
> [!NOTE]
>  <span data-ttu-id="e394c-128">此外可以将上面的代码添加到 WCF 扩展选项卡。如果扩展需要在接收端，请参阅**\<主机名\>属性对话框中，WCF 扩展**选项卡 （WCF 自定义或 WCF CustomIsolated 适配器接收处理程序） [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="e394c-128">The above code can also be added to the WCF Extensions tab. If the extension needs to be on the receive side, see the **\<Host Name\> Properties Dialog Box, WCF Extensions** tab (WCF-Custom or WCF-CustomIsolated Adapter Receive Handler) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="e394c-129">如果扩展需要在发送端，请参阅**\<主机名\>属性对话框中，WCF 扩展**选项卡 （WCF 自定义适配器发送处理程序） [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="e394c-129">If the extension needs to be on the send side, see **\<Host Name\> Properties Dialog Box, WCF Extensions** tab (WCF-Custom Adapter Send Handler) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 3. <span data-ttu-id="e394c-130">关闭并重新打开管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e394c-130">Close and reopen your admin console.</span></span> <span data-ttu-id="e394c-131">您应该能够在 WCF-Custom 适配器中查看您的自定义行为，并且当您启用时端口应保持启用状态。</span><span class="sxs-lookup"><span data-stu-id="e394c-131">You should be able to see your custom behavior in the WCF-Custom adapter, and the port should stay enabled when you enable it.</span></span>