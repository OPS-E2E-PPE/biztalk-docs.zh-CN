---
title: InfoPath 消息模板 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb055b1-8480-44dd-8739-f2981bca63c3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c929e8ef1edcd88c0976d145354779b3e095634
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024467"
---
# <a name="the-infopath-message-template"></a><span data-ttu-id="094a5-102">InfoPath 消息模板</span><span class="sxs-lookup"><span data-stu-id="094a5-102">The InfoPath Message Template</span></span>
<span data-ttu-id="094a5-103">作为 ESB 管理门户中查看 ESB 错误消息的替代方法，用户可以充分利用一个名为 ESB 异常的消息查看器，随一起提供的 Microsoft InfoPath 消息模板[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="094a5-103">As an alternative to viewing ESB fault messages in the ESB Management Portal, users can take advantage of a Microsoft InfoPath message template named the ESB Exception Message Viewer, provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="094a5-104">ESB 异常管理框架可以保留序列化格式，以及 ESB 异常消息查看器模板中，将显示错误消息和它包含原始消息的多个视图中的消息。</span><span class="sxs-lookup"><span data-stu-id="094a5-104">The ESB Exception Management Framework can persist messages in a serialized format that, together with the ESB Exception Message Viewer template, will display several views of the fault message and the original messages it contains.</span></span> <span data-ttu-id="094a5-105">ESB 异常消息查看器提供了以下视图：</span><span class="sxs-lookup"><span data-stu-id="094a5-105">The ESB Exception Message Viewer provides the following views:</span></span>  
  
- <span data-ttu-id="094a5-106">常规视图</span><span class="sxs-lookup"><span data-stu-id="094a5-106">General view</span></span>  
  
- <span data-ttu-id="094a5-107">异常对象视图</span><span class="sxs-lookup"><span data-stu-id="094a5-107">Exception Object view</span></span>  
  
- <span data-ttu-id="094a5-108">消息视图 (Messages view)</span><span class="sxs-lookup"><span data-stu-id="094a5-108">Messages view</span></span>  
  
  <span data-ttu-id="094a5-109">图 1 显示了 ESB 异常消息查看器，后者将显示最异常的环境属性的常规视图。</span><span class="sxs-lookup"><span data-stu-id="094a5-109">Figure 1 shows the General view of the ESB Exception Message Viewer, which displays most ambient properties of the exception.</span></span>  
  
  <span data-ttu-id="094a5-110">![异常消息常规视图](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4-ExceptionMessageGeneralView")</span><span class="sxs-lookup"><span data-stu-id="094a5-110">![Exception Message General View](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4-ExceptionMessageGeneralView")</span></span>  
  
  <span data-ttu-id="094a5-111">**图 1**</span><span class="sxs-lookup"><span data-stu-id="094a5-111">**Figure 1**</span></span>  
  
  <span data-ttu-id="094a5-112">**ESB 异常消息查看器显示常规视图**</span><span class="sxs-lookup"><span data-stu-id="094a5-112">**The ESB Exception Message Viewer showing the General view**</span></span>  
  
  <span data-ttu-id="094a5-113">图 2 显示了异常对象视图，其中显示的属性和从堆栈跟踪**System.Exception**对象。</span><span class="sxs-lookup"><span data-stu-id="094a5-113">Figure 2 shows the Exception Object view, which displays the properties and the stack trace from the **System.Exception** object.</span></span>  
  
  <span data-ttu-id="094a5-114">![异常消息异常对象](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4-ExceptionMessageExceptionObject")</span><span class="sxs-lookup"><span data-stu-id="094a5-114">![Exception Message Exception Object](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4-ExceptionMessageExceptionObject")</span></span>  
  
  <span data-ttu-id="094a5-115">**图 2**</span><span class="sxs-lookup"><span data-stu-id="094a5-115">**Figure 2**</span></span>  
  
  <span data-ttu-id="094a5-116">**ESB 异常消息查看器显示异常对象视图**</span><span class="sxs-lookup"><span data-stu-id="094a5-116">**The ESB Exception Message Viewer showing the Exception Object view**</span></span>  
  
  <span data-ttu-id="094a5-117">图 3 显示了消息视图，它提供的下拉列表，用户可以从中选择从可用的持久消息。</span><span class="sxs-lookup"><span data-stu-id="094a5-117">Figure 3 shows the Messages view, which provides a drop-down list from which the user can select from available persisted messages.</span></span> <span data-ttu-id="094a5-118">该视图显示持久的消息和 XML 消息内容的上下文属性的值。</span><span class="sxs-lookup"><span data-stu-id="094a5-118">The view displays the values of the context properties of the persisted message and the XML message content.</span></span>  
  
  <span data-ttu-id="094a5-119">![异常消息消息视图](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4-ExceptionMessageMessagesView")</span><span class="sxs-lookup"><span data-stu-id="094a5-119">![Exception Message Messages View](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4-ExceptionMessageMessagesView")</span></span>  
  
  <span data-ttu-id="094a5-120">**图 3**</span><span class="sxs-lookup"><span data-stu-id="094a5-120">**Figure 3**</span></span>  
  
  <span data-ttu-id="094a5-121">**ESB 异常消息查看器显示的消息视图**</span><span class="sxs-lookup"><span data-stu-id="094a5-121">**The ESB Exception Message Viewer showing the Messages view**</span></span>