---
title: 处理外部提交的异常通过自定义处理程序 |Microsoft Docs
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
ms.openlocfilehash: 6ec780adcc28318eb76c3dd00aa1f5081323105b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400790"
---
# <a name="handling-externally-submitted-exceptions-using-a-custom-handler"></a><span data-ttu-id="e1617-102">处理外部提交的异常通过自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="e1617-102">Handling Externally Submitted Exceptions Using a Custom Handler</span></span>
<span data-ttu-id="e1617-103">在此用例，外部客户端将提交一条异常消息通过 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="e1617-103">In this use case, an external client submits an exception message through a Web service.</span></span> <span data-ttu-id="e1617-104">使用 ESB 异常编码器管道组件，预配置的发送端口订阅错误消息;它处理并将其保存为磁盘文件，您可以使用 Microsoft InfoPath 中图 1 所示。</span><span class="sxs-lookup"><span data-stu-id="e1617-104">A send port, preconfigured with the ESB Exception Encoder pipeline component, subscribes to the fault message; it processes and persists it as a disk file that you can view using Microsoft InfoPath, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="e1617-105">![处理外部异常](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3-HandlingExternalExceptions")</span><span class="sxs-lookup"><span data-stu-id="e1617-105">![Handling External Exceptions](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3-HandlingExternalExceptions")</span></span>  
  
 <span data-ttu-id="e1617-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="e1617-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="e1617-107">**处理传入的异常或错误消息并将保存到磁盘文件**</span><span class="sxs-lookup"><span data-stu-id="e1617-107">**Handling incoming exception or fault messages and persisting to a disk file**</span></span>  
  
 <span data-ttu-id="e1617-108">异常处理服务示例中包含[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="e1617-108">The Exception Handling Service Sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="e1617-109">它演示如何使用 ESB 异常服务作为通用机制来提交，将存储在外部应用程序中的错误消息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]异常管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e1617-109">It shows how to use the ESB Exception Service as a universal mechanism to submit fault messages from external applications that will be stored in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] exception management database.</span></span> <span data-ttu-id="e1617-110">有关详细信息，请参阅[运行异常处理服务示例](../esb-toolkit/running-the-exception-handling-service-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e1617-110">For more information, see [Running the Exception Handling Service Sample](../esb-toolkit/running-the-exception-handling-service-sample.md).</span></span>