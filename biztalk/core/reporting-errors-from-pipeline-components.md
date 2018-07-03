---
title: 报告来自管道组件的错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IErrorInfo object
- pipeline components [custom], errors
- SetErrorInfo method
- Exception object
ms.assetid: ad7c519e-829a-4a92-a42f-3e367d5dbaa8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a979b894715055b979ecae8c66ecb3fa19ba603
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018119"
---
# <a name="reporting-errors-from-pipeline-components"></a><span data-ttu-id="10ea0-102">报告来自管道组件的错误</span><span class="sxs-lookup"><span data-stu-id="10ea0-102">Reporting Errors from Pipeline Components</span></span>
<span data-ttu-id="10ea0-103">管道组件用两种方式报告错误：</span><span class="sxs-lookup"><span data-stu-id="10ea0-103">Pipeline components report errors in two ways:</span></span>  
  
-   <span data-ttu-id="10ea0-104">对于基于 .NET 的组件，通过引发异常。</span><span class="sxs-lookup"><span data-stu-id="10ea0-104">For .NET-based components, by throwing an exception.</span></span>  
  
-   <span data-ttu-id="10ea0-105">对于基于 COM 的组件，通过设置**ErrorInfo**对象并返回失败 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="10ea0-105">For COM-based components, by setting the **ErrorInfo** object and returning a failure HRESULT.</span></span>  
  
## <a name="reporting-errors-from-net-pipeline-components"></a><span data-ttu-id="10ea0-106">报告来自 .NET 管道组件的错误</span><span class="sxs-lookup"><span data-stu-id="10ea0-106">Reporting errors from .NET pipeline components</span></span>  
 <span data-ttu-id="10ea0-107">若要报告某一错误，基于 .NET 的管道组件需要引发一个异常，以便报告错误说明。</span><span class="sxs-lookup"><span data-stu-id="10ea0-107">To report an error, a .NET-based pipeline component needs to throw an exception where it reports the error description.</span></span> <span data-ttu-id="10ea0-108">若要报告引发错误的组件的名称，设置**源**的属性**异常**对象。</span><span class="sxs-lookup"><span data-stu-id="10ea0-108">To report the name of the component that throws an error, set the **Source** property of the **Exception** object.</span></span>  
  
 <span data-ttu-id="10ea0-109">消息引擎将使用**消息**并**源**的属性**异常**对象来报告错误。</span><span class="sxs-lookup"><span data-stu-id="10ea0-109">The Messaging Engine uses the **Message** and **Source** properties of the **Exception** object to report an error.</span></span> <span data-ttu-id="10ea0-110">下面的消息将写入事件日志：</span><span class="sxs-lookup"><span data-stu-id="10ea0-110">The following message is written to the event log:</span></span>  
  
 <span data-ttu-id="10ea0-111">"出现故障执行 [接收&#124;发送] 管道：\<管道名称\>源：\<源\>[接收位置&#124;发送端口:]\<位置&#124;的端口名称\>原因：\<消息\>。"</span><span class="sxs-lookup"><span data-stu-id="10ea0-111">"There was a failure executing the [receive&#124;send] pipeline: \<pipeline name\> Source: \<Source\> [Receive Location&#124;Send Port:] \<location&#124;port name\> Reason: \<Message\>."</span></span>  
  
## <a name="reporting-errors-from-com-pipeline-components"></a><span data-ttu-id="10ea0-112">报告来自 COM 管道组件的错误</span><span class="sxs-lookup"><span data-stu-id="10ea0-112">Reporting errors from COM pipeline components</span></span>  
 <span data-ttu-id="10ea0-113">若要报告某一错误，基于 COM 的管道组件快执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="10ea0-113">To report an error, COM-based pipeline components perform the following actions:</span></span>  
  
1. <span data-ttu-id="10ea0-114">管道组件集**IErrorInfo**对象通过调用**SetErrorInfo**方法。</span><span class="sxs-lookup"><span data-stu-id="10ea0-114">The pipeline component sets the **IErrorInfo** object by calling the **SetErrorInfo** method.</span></span>  
  
2. <span data-ttu-id="10ea0-115">管道组件将失败的 HRESULT 返回到消息引擎。</span><span class="sxs-lookup"><span data-stu-id="10ea0-115">The pipeline component returns a failed HRESULT to the Messaging Engine.</span></span>  
  
   <span data-ttu-id="10ea0-116">消息引擎将使用**GetSource**并**GetDescription**的属性**IErrorInfo**对象来报告错误。</span><span class="sxs-lookup"><span data-stu-id="10ea0-116">The Messaging Engine uses the **GetSource** and **GetDescription** properties of the **IErrorInfo** object to report an error.</span></span> <span data-ttu-id="10ea0-117">如果未设置源，则使用该组件的名称。</span><span class="sxs-lookup"><span data-stu-id="10ea0-117">If the source is not set, the name of the component is used.</span></span> <span data-ttu-id="10ea0-118">如果在说明不组或整个**ErrorInfo**未设置对象，则返回的 HRESULT 报告而不是说明。</span><span class="sxs-lookup"><span data-stu-id="10ea0-118">If the description is not set or the whole **ErrorInfo** object is not set, the returned HRESULT is reported instead of the description.</span></span> <span data-ttu-id="10ea0-119">下面的消息将写入事件日志：</span><span class="sxs-lookup"><span data-stu-id="10ea0-119">The following message is written to the event log:</span></span>  
  
   <span data-ttu-id="10ea0-120">"出现故障执行 [接收&#124;发送] 管道：\<管道名称\>源： \<GetSource\> [接收位置&#124;发送端口:]\<位置&#124;端口名称\>原因： \<GetDescription 或 HRESULT\>。"</span><span class="sxs-lookup"><span data-stu-id="10ea0-120">"There was a failure executing the [receive&#124;send] pipeline: \<pipeline name\> Source: \<GetSource\> [Receive Location&#124;Send Port:] \<location&#124;port name\> Reason: \<GetDescription or HRESULT\>."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ea0-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="10ea0-121">See Also</span></span>  
 [<span data-ttu-id="10ea0-122">开发自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="10ea0-122">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)