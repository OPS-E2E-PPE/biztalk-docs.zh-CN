---
title: 如何添加错误 Message1 |Microsoft 文档
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
ms.openlocfilehash: 87ef85460f6ca6aea046ef9efff60fd198664cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246645"
---
# <a name="how-to-add-a-fault-message"></a><span data-ttu-id="8c382-102">如何添加错误消息</span><span class="sxs-lookup"><span data-stu-id="8c382-102">How to Add a Fault Message</span></span>
<span data-ttu-id="8c382-103">首次创建通向后端系统的端口时，该端口中包含了请求和响应通信。</span><span class="sxs-lookup"><span data-stu-id="8c382-103">When you first created the port to the back-end system, it contained a request and a response.</span></span> <span data-ttu-id="8c382-104">必须添加错误来捕获异常。</span><span class="sxs-lookup"><span data-stu-id="8c382-104">You must add a fault to capture the exception.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="8c382-105">添加错误消息</span><span class="sxs-lookup"><span data-stu-id="8c382-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="8c382-106">右键单击**端口操作**，然后选择**新的错误消息**。</span><span class="sxs-lookup"><span data-stu-id="8c382-106">Right-click **Port Operation**, and then select a **New Fault Message**.</span></span>  
  
     <span data-ttu-id="8c382-107">A**错误**下显示**请求和响应**端口中。</span><span class="sxs-lookup"><span data-stu-id="8c382-107">A **Fault** appears under the **Request and Response** in the port.</span></span>  
  
2.  <span data-ttu-id="8c382-108">上**业务流程视图**屏幕上，右键单击**消息**，然后选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="8c382-108">On the **Orchestration View** screen, right-click **Messages**, and then select **New Message**.</span></span>  
  
     <span data-ttu-id="8c382-109">由此将创建 Message_3，您可将其明确分配给该错误。</span><span class="sxs-lookup"><span data-stu-id="8c382-109">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
3.  <span data-ttu-id="8c382-110">右键单击**Message_3**访问**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="8c382-110">Right-click **Message_3** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="8c382-111">设置**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="8c382-111">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="8c382-112">选择**架构**，然后选择从**ref 程序集**。</span><span class="sxs-lookup"><span data-stu-id="8c382-112">Select **Schema**, and then select from **ref assembly**.</span></span>  
  
         <span data-ttu-id="8c382-113">这将打开**选择项目类型**窗口。</span><span class="sxs-lookup"><span data-stu-id="8c382-113">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="8c382-114">向下滚动选择该完全限定的错误。</span><span class="sxs-lookup"><span data-stu-id="8c382-114">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="8c382-115">名称是**BTS。SOAP_Envelope_1__1.fault**。</span><span class="sxs-lookup"><span data-stu-id="8c382-115">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span> <span data-ttu-id="8c382-116">单击**确定**以接受所选内容并关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="8c382-116">Click **OK** to accept the selection and close the window.</span></span>  
  
4.  <span data-ttu-id="8c382-117">右键单击**错误**访问**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="8c382-117">Right-click the **Fault** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="8c382-118">设置**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="8c382-118">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="8c382-119">选择**架构**，然后选择从**ref**程序集。</span><span class="sxs-lookup"><span data-stu-id="8c382-119">Select **Schema** and then select from **ref** assembly.</span></span>  
  
         <span data-ttu-id="8c382-120">这将打开**选择项目类型**窗口。</span><span class="sxs-lookup"><span data-stu-id="8c382-120">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="8c382-121">向下滚动选择该完全限定的错误。</span><span class="sxs-lookup"><span data-stu-id="8c382-121">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="8c382-122">名称是**BTS。SOAP_Envelope_1__1.fault**。</span><span class="sxs-lookup"><span data-stu-id="8c382-122">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span>  
  
    4.  <span data-ttu-id="8c382-123">单击**确定**以接受所选内容并关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="8c382-123">Click **OK** to accept the selection and close the window.</span></span>  
  
         ![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")  
  
5.  <span data-ttu-id="8c382-124">对该错误命名后，您需将此名称的类型设置为 CatchException 的异常对象类型。</span><span class="sxs-lookup"><span data-stu-id="8c382-124">After the fault is named, you will set this name to the CatchException's exception object type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c382-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c382-125">See Also</span></span>  
 [<span data-ttu-id="8c382-126">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="8c382-126">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)