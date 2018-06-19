---
title: 测试 JMS MQRFH2 示例安装 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 965e985d-f0fe-4b0f-b01b-cf98d1e2f6a4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5970f12479cddfb6a635cbd00dd139495a2f6242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294613"
---
# <a name="test-the-jms-mqrfh2-sample-installation"></a><span data-ttu-id="479e8-102">测试 JMS MQRFH2 示例安装</span><span class="sxs-lookup"><span data-stu-id="479e8-102">Test the JMS MQRFH2 Sample Installation</span></span>
<span data-ttu-id="479e8-103">你可以检查成功地安装和操作的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]JMS MQRFH2 示例之前执行任何示例方案。</span><span class="sxs-lookup"><span data-stu-id="479e8-103">You can check for successful installation and operation of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] JMS MQRFH2 sample before you execute any of the sample scenarios.</span></span>  
  
 <span data-ttu-id="479e8-104">**若要测试 JMS MQRFH2 示例安装**</span><span class="sxs-lookup"><span data-stu-id="479e8-104">**To test the JMS MQRFH2 sample installation**</span></span>  
  
1.  <span data-ttu-id="479e8-105">使用"RFHUtil"JMS 测试实用程序 \Source\Samples\JMS\Test\Data\Load 文件夹中的测试消息写入名为 ESB 的队列。JMS。示例。SENDTOBIZTALK。</span><span class="sxs-lookup"><span data-stu-id="479e8-105">Use the "RFHUtil" JMS test utility to write the test messages in the \Source\Samples\JMS\Test\Data\Load folder to the queue named ESB.JMS.SAMPLE.SENDTOBIZTALK.</span></span>  
  
2.  <span data-ttu-id="479e8-106">此示例将消息发送到目标队列和到答复队列消息的副本。</span><span class="sxs-lookup"><span data-stu-id="479e8-106">The sample sends the message to the destination queue and a copy of the message to the reply queue.</span></span>