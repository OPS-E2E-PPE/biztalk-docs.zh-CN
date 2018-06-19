---
title: ValidationAdapter |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe99350-14c0-4ddb-b257-af9a0c4258f6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a325a561017c6efaf6d6aefe2e271c834c13a363
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966435"
---
# <a name="validationadapter"></a><span data-ttu-id="85e97-102">ValidationAdapter</span><span class="sxs-lookup"><span data-stu-id="85e97-102">ValidationAdapter</span></span>
<span data-ttu-id="85e97-103">该 ValidationAdapter 示例演示了如何对响应方公用流程中的消息运行特殊验证规则。</span><span class="sxs-lookup"><span data-stu-id="85e97-103">The ValidationAdapter sample demonstrates how to run special validation rules on a message in a responder public process.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="85e97-104">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 本身在发送或接收管道以及业务流程中执行验证。</span><span class="sxs-lookup"><span data-stu-id="85e97-104">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] natively performs validation in the send or receive pipeline, and in orchestrations.</span></span> <span data-ttu-id="85e97-105">如果要执行其他验证，可以创建验证适配器。</span><span class="sxs-lookup"><span data-stu-id="85e97-105">If you want to perform additional validation, you can create a validation adapter.</span></span> <span data-ttu-id="85e97-106">其他验证可以包括无法使用 XSD 实现的跨字段验证规则或业务特定的验证规则。</span><span class="sxs-lookup"><span data-stu-id="85e97-106">The additional validation could include cross-field validation or business-specific validation rules that you cannot implement using an XSD.</span></span>  
  
 <span data-ttu-id="85e97-107">你可以通过添加创建的验证适配器[!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)]ValidationAdapter 示例中，发布了接口，和的协议属性中输入适配器的代码。</span><span class="sxs-lookup"><span data-stu-id="85e97-107">You can create a validation adapter by adding [!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)] code to the ValidationAdapter sample, publishing the interfaces, and entering the adapter into the agreement properties.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="85e97-108">消息处理过程中将然后调用该验证适配器。</span><span class="sxs-lookup"><span data-stu-id="85e97-108"> will then call the validation adapter during message processing.</span></span>  
  
 <span data-ttu-id="85e97-109">由于 ValidationAdapter 由公用业务流程使用，因此，ValidationAdapter 运行时使用的凭据与该业务流程的宿主 BizTalk 主机服务的凭据相同。</span><span class="sxs-lookup"><span data-stu-id="85e97-109">Since the ValidationAdapter is used by the public process orchestration , it runs under the same credentials as the BizTalk host service hosting that orchestration.</span></span>  
  
 <span data-ttu-id="85e97-110">ValidationAdapter 示例位于\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>RosettaNet\SDK\ 快捷键ValidationAdapter。</span><span class="sxs-lookup"><span data-stu-id="85e97-110">The ValidationAdapter sample is located in \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for RosettaNet\SDK\ValidationAdapter.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="85e97-111">演示</span><span class="sxs-lookup"><span data-stu-id="85e97-111">Demonstrates</span></span>  
 <span data-ttu-id="85e97-112">ValidationAdapter 示例演示如何验证服务内容中的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="85e97-112">The ValidationAdapter sample demonstrates validation of the e-mail address in the service content.</span></span> <span data-ttu-id="85e97-113">该示例实现 `IValidateRNIFMessageParts` 接口。</span><span class="sxs-lookup"><span data-stu-id="85e97-113">The sample implements the `IValidateRNIFMessageParts` interface.</span></span> <span data-ttu-id="85e97-114">如果电子邮件地址的格式不正确，它将返回 `RNIFException`。</span><span class="sxs-lookup"><span data-stu-id="85e97-114">It returns an `RNIFException` if the e-mail address is not in the correct format.</span></span> <span data-ttu-id="85e97-115">XML 文档**preambleToValidate**， **serviceHeaderToValidate**， **deliveryHeaderToValidate**，和**serviceContentToValidate**定义验证。</span><span class="sxs-lookup"><span data-stu-id="85e97-115">The XML documents **preambleToValidate**, **serviceHeaderToValidate**, **deliveryHeaderToValidate**, and **serviceContentToValidate** define the validation.</span></span>  
  
 <span data-ttu-id="85e97-116">ValidationAdapter 使用 RNIFerror.IsOkToSendException 属性来确定在发生错误时要发送的消息种类。</span><span class="sxs-lookup"><span data-stu-id="85e97-116">The ValidationAdapter uses the RNIFerror.IsOkToSendException property to determine what kind of message to send in the event of an error.</span></span> <span data-ttu-id="85e97-117">如果验证不成功，则 ValidationAdapter 将 RNIFerror.ErrorCode 设置为一个非零值。</span><span class="sxs-lookup"><span data-stu-id="85e97-117">If validation does not succeed, the ValidationAdapter sets RNIFerror.ErrorCode to a non-zero value.</span></span> <span data-ttu-id="85e97-118">如果 RNIFerror.IsOkToSendException 属性为 true，则流程将发送一个负的确认值。</span><span class="sxs-lookup"><span data-stu-id="85e97-118">If RNIFerror.IsOkToSendException property is true, the process sends a negative acknowledgment.</span></span> <span data-ttu-id="85e97-119">对于 RNIF 2.0，它是异常消息。</span><span class="sxs-lookup"><span data-stu-id="85e97-119">For RNIF 2.0, this is an exception message.</span></span> <span data-ttu-id="85e97-120">对于 RNIF 1.1，它是确认回执异常消息。</span><span class="sxs-lookup"><span data-stu-id="85e97-120">For RNIF 1.1, this is a receipt acknowledgment exception message.</span></span> <span data-ttu-id="85e97-121">如果 RNIFerror.IsOkToSendException 属性为 false 并且配置了 0A1，则流程将发送 0A1 消息。</span><span class="sxs-lookup"><span data-stu-id="85e97-121">If RNIFerror.IsOkToSendException property is false and 0A1 is configured, the process will send a 0A1 message.</span></span> <span data-ttu-id="85e97-122">流程发送异常消息、确认回执异常消息或 0A1 消息后，它将终止运行。</span><span class="sxs-lookup"><span data-stu-id="85e97-122">Once the process sends an exception message, receipt acknowledgment exception message, or 0A1 message, it will terminate.</span></span>  
  
 <span data-ttu-id="85e97-123">如果 RNIFerror.IsOkToSendException 属性为 false 但未配置 0A1，则流程将不发送异常消息，也不发送 0A1。</span><span class="sxs-lookup"><span data-stu-id="85e97-123">If RNIFerror.IsOkToSendException property is false and 0A1 is not configured, the process will send neither an exception nor a 0A1.</span></span> <span data-ttu-id="85e97-124">它将记录错误然后终止运行。</span><span class="sxs-lookup"><span data-stu-id="85e97-124">It will log the error and then terminate.</span></span>  
  
 <span data-ttu-id="85e97-125">如果验证成功，则 ValidationAdapter 将 RNIFerror.ErrorCode 设置为 0，BTARN 将消息路由至专用流程。</span><span class="sxs-lookup"><span data-stu-id="85e97-125">If validation succeeds, the ValidationAdapter sets RNIFerror.ErrorCode to 0, and BTARN routes the message to the private process.</span></span> <span data-ttu-id="85e97-126">只有验证成功后，BTARN 才将消息路由到专用流程。</span><span class="sxs-lookup"><span data-stu-id="85e97-126">It routes the message to the private process only if validation is successful.</span></span>  
  
## <a name="to-implement-this-sample"></a><span data-ttu-id="85e97-127">实现此示例</span><span class="sxs-lookup"><span data-stu-id="85e97-127">To Implement this Sample</span></span>  
 <span data-ttu-id="85e97-128">若要实现该 ValidationAdapter 示例，必须向协议中添加验证适配器。</span><span class="sxs-lookup"><span data-stu-id="85e97-128">To implement the ValidationAdapter sample, you must add the validation adapter to the agreement.</span></span>  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a><span data-ttu-id="85e97-129">向协议中添加验证适配器</span><span class="sxs-lookup"><span data-stu-id="85e97-129">To add the validation adapter to the agreement</span></span>  
  
1.  <span data-ttu-id="85e97-130">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="85e97-130">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="85e97-131">在[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="85e97-131">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click **Agreements**.</span></span>  
  
3.  <span data-ttu-id="85e97-132">双击要添加验证适配器的协议。</span><span class="sxs-lookup"><span data-stu-id="85e97-132">Double-click the agreement to which you want to add the validation adapter.</span></span>  
  
4.  <span data-ttu-id="85e97-133">在**验证适配器**对话框框中，单击省略号按钮 (**...**) 的右侧的按钮**程序集名称**，移到包含验证适配器程序集的位置，选择相应的.dll 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="85e97-133">In the **Validation Adapter** dialog box, click the ellipsis button (**...**) button to the right of **Assembly name**, move to the location that contains the validation adapter assembly, select the appropriate .dll file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="85e97-134">单击向下的箭头**类名**，选择验证适配器类，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="85e97-134">Click the down arrow for **Class Name**, select the validation adapter class, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e97-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85e97-135">See Also</span></span>  
 [<span data-ttu-id="85e97-136">适配器示例</span><span class="sxs-lookup"><span data-stu-id="85e97-136">Adapter Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)