---
title: 处理外部提交使用自定义处理的异常 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53fa661e-d391-47c0-92d5-1d0c45b5963d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ba3fc49756619f77188f0a311ff46eb18e7f0b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294053"
---
# <a name="handling-externally-submitted-exceptions-using-a-custom-handler"></a><span data-ttu-id="360ca-102">处理外部提交使用自定义处理的异常</span><span class="sxs-lookup"><span data-stu-id="360ca-102">Handling Externally Submitted Exceptions Using a Custom Handler</span></span>
<span data-ttu-id="360ca-103">在使用此种情况下，外部客户端将提交一条异常消息通过 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="360ca-103">In this use case, an external client submits an exception message through a Web service.</span></span> <span data-ttu-id="360ca-104">发送端口，预先配置为使用 ESB 异常编码器管道组件，订阅的错误消息;它处理，并将其保存为磁盘文件，以便你可以查看使用 Microsoft InfoPath 中图 1 所示。</span><span class="sxs-lookup"><span data-stu-id="360ca-104">A send port, preconfigured with the ESB Exception Encoder pipeline component, subscribes to the fault message; it processes and persists it as a disk file that you can view using Microsoft InfoPath, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="360ca-105">![处理外部异常](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3 HandlingExternalExceptions")</span><span class="sxs-lookup"><span data-stu-id="360ca-105">![Handling External Exceptions](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3-HandlingExternalExceptions")</span></span>  
  
 <span data-ttu-id="360ca-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="360ca-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="360ca-107">**处理传入的异常或错误消息并将保存到磁盘文件**</span><span class="sxs-lookup"><span data-stu-id="360ca-107">**Handling incoming exception or fault messages and persisting to a disk file**</span></span>  
  
 <span data-ttu-id="360ca-108">在异常处理服务示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="360ca-108">The Exception Handling Service Sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="360ca-109">它演示如何使用作为通用机制 ESB 异常服务提交从外部应用程序将存储在错误消息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]异常管理数据库。</span><span class="sxs-lookup"><span data-stu-id="360ca-109">It shows how to use the ESB Exception Service as a universal mechanism to submit fault messages from external applications that will be stored in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] exception management database.</span></span> <span data-ttu-id="360ca-110">有关详细信息，请参阅[运行异常处理服务示例](../esb-toolkit/running-the-exception-handling-service-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="360ca-110">For more information, see [Running the Exception Handling Service Sample](../esb-toolkit/running-the-exception-handling-service-sample.md).</span></span>