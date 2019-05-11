---
title: 如何添加容错 Message1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- fault messages, adding
- adding, fault messages
- faults, adding messages
ms.assetid: 9d21de6b-c1a5-46e9-a9dc-d6aa7b5fe34b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed9bcaab8db10ee0be664b02028af9b9a79981d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343847"
---
# <a name="how-to-add-a-fault-message"></a><span data-ttu-id="824c1-102">如何添加错误消息</span><span class="sxs-lookup"><span data-stu-id="824c1-102">How to Add a Fault Message</span></span>
<span data-ttu-id="824c1-103">当你首次创建该端口与后端系统时，它包含请求和响应。</span><span class="sxs-lookup"><span data-stu-id="824c1-103">When you first created the port to the back-end system, it contained a request and a response.</span></span> <span data-ttu-id="824c1-104">您必须添加错误来捕获异常。</span><span class="sxs-lookup"><span data-stu-id="824c1-104">You must add a fault to capture the exception.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="824c1-105">若要添加错误消息</span><span class="sxs-lookup"><span data-stu-id="824c1-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="824c1-106">右键单击**端口操作**，然后选择**新建错误消息**。</span><span class="sxs-lookup"><span data-stu-id="824c1-106">Right-click **Port Operation**, and then select a **New Fault Message**.</span></span>  
  
     <span data-ttu-id="824c1-107">一个**容错**下显示**请求和响应**端口中。</span><span class="sxs-lookup"><span data-stu-id="824c1-107">A **Fault** appears under the **Request and Response** in the port.</span></span>  
  
2.  <span data-ttu-id="824c1-108">上**业务流程视图**屏幕上，右键单击**消息**，然后选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="824c1-108">On the **Orchestration View** screen, right-click **Messages**, and then select **New Message**.</span></span>  
  
     <span data-ttu-id="824c1-109">这将创建 Message_3，您可以将其分配特定于该错误。</span><span class="sxs-lookup"><span data-stu-id="824c1-109">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
3.  <span data-ttu-id="824c1-110">右键单击**Message_3**访问**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="824c1-110">Right-click **Message_3** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="824c1-111">设置**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="824c1-111">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="824c1-112">选择**架构**，然后选择从**引用程序集**。</span><span class="sxs-lookup"><span data-stu-id="824c1-112">Select **Schema**, and then select from **ref assembly**.</span></span>  
  
         <span data-ttu-id="824c1-113">这将打开**选择项目类型**窗口。</span><span class="sxs-lookup"><span data-stu-id="824c1-113">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="824c1-114">向下滚动并选择完全限定的错误。</span><span class="sxs-lookup"><span data-stu-id="824c1-114">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="824c1-115">名称是**BTS。SOAP_Envelope_1__1.fault**。</span><span class="sxs-lookup"><span data-stu-id="824c1-115">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span> <span data-ttu-id="824c1-116">单击**确定**以接受选择并关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="824c1-116">Click **OK** to accept the selection and close the window.</span></span>  
  
4.  <span data-ttu-id="824c1-117">右键单击**容错**访问**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="824c1-117">Right-click the **Fault** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="824c1-118">设置**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="824c1-118">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="824c1-119">选择**架构**然后选择从**ref**程序集。</span><span class="sxs-lookup"><span data-stu-id="824c1-119">Select **Schema** and then select from **ref** assembly.</span></span>  
  
         <span data-ttu-id="824c1-120">这将打开**选择项目类型**窗口。</span><span class="sxs-lookup"><span data-stu-id="824c1-120">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="824c1-121">向下滚动并选择完全限定的错误。</span><span class="sxs-lookup"><span data-stu-id="824c1-121">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="824c1-122">名称是**BTS。SOAP_Envelope_1__1.fault**。</span><span class="sxs-lookup"><span data-stu-id="824c1-122">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span>  
  
    4.  <span data-ttu-id="824c1-123">单击**确定**以接受选择并关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="824c1-123">Click **OK** to accept the selection and close the window.</span></span>  
  
         <span data-ttu-id="824c1-124">![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")</span><span class="sxs-lookup"><span data-stu-id="824c1-124">![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")</span></span>  
  
5.  <span data-ttu-id="824c1-125">该错误命名后，您将此名称设置为 CatchException 的异常对象类型。</span><span class="sxs-lookup"><span data-stu-id="824c1-125">After the fault is named, you will set this name to the CatchException's exception object type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824c1-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="824c1-126">See Also</span></span>  
 [<span data-ttu-id="824c1-127">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="824c1-127">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)