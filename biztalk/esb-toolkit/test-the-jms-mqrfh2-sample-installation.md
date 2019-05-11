---
title: 测试 JMS MQRFH2 示例安装 |Microsoft Docs
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
ms.openlocfilehash: d22f609ef8de65845ff36cc1e60b2942faa956de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268668"
---
# <a name="test-the-jms-mqrfh2-sample-installation"></a><span data-ttu-id="34685-102">测试 JMS MQRFH2 示例安装</span><span class="sxs-lookup"><span data-stu-id="34685-102">Test the JMS MQRFH2 Sample Installation</span></span>
<span data-ttu-id="34685-103">你可以检查成功安装和操作的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]JMS MQRFH2 示例之前执行任何示例方案。</span><span class="sxs-lookup"><span data-stu-id="34685-103">You can check for successful installation and operation of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] JMS MQRFH2 sample before you execute any of the sample scenarios.</span></span>  
  
 <span data-ttu-id="34685-104">**若要测试 JMS MQRFH2 示例安装**</span><span class="sxs-lookup"><span data-stu-id="34685-104">**To test the JMS MQRFH2 sample installation**</span></span>  
  
1.  <span data-ttu-id="34685-105">使用"RFHUtil"JMS 测试实用程序将 \Source\Samples\JMS\Test\Data\Load 文件夹中的测试消息写入名为 ESB 的队列。JMS。示例。SENDTOBIZTALK。</span><span class="sxs-lookup"><span data-stu-id="34685-105">Use the "RFHUtil" JMS test utility to write the test messages in the \Source\Samples\JMS\Test\Data\Load folder to the queue named ESB.JMS.SAMPLE.SENDTOBIZTALK.</span></span>  
  
2.  <span data-ttu-id="34685-106">该示例将消息发送到目标队列和到答复队列消息的副本。</span><span class="sxs-lookup"><span data-stu-id="34685-106">The sample sends the message to the destination queue and a copy of the message to the reply queue.</span></span>