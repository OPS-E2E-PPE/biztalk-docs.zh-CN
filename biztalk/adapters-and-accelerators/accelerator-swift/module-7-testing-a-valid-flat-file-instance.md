---
title: 模块 7:测试的有效的平面文件实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, flat file instance
- tutorial, testing flat file instance
- flat files, testing
ms.assetid: ba8a5d81-41b0-4da7-8c2e-02cf29953af7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f9efe9cc113725809428dd66a91c6d4d28bbb08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377125"
---
# <a name="module-7-testing-a-valid-flat-file-instance"></a><span data-ttu-id="ff513-102">模块 7:测试的有效的平面文件实例</span><span class="sxs-lookup"><span data-stu-id="ff513-102">Module 7: Testing a Valid Flat File Instance</span></span>
<span data-ttu-id="ff513-103">在此模块中，提交有效示例的文件的平面文件接收端口上一个实验室中创建的 MT103。</span><span class="sxs-lookup"><span data-stu-id="ff513-103">In this module, you submit a valid sample MT103 flat file to the file receive ports created in the previous labs.</span></span> <span data-ttu-id="ff513-104">此任务用于测试你在上一个实验室中创建的接收管道。</span><span class="sxs-lookup"><span data-stu-id="ff513-104">This task tests the receive pipelines you created in previous labs.</span></span> <span data-ttu-id="ff513-105">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]将以 XML 格式的输出写入到在上一课中，选择的发送端口中的输出文件夹[第 2 课：添加 XML 发送端口](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="ff513-105">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] writes the output in XML format to the output folder in the send port you selected in the previous lesson, [Lesson 2: Adding an XML Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span></span>  
  
 <span data-ttu-id="ff513-106">启动文件接收适配器的将 SWIFT 的平面格式的文件复制到入站的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ff513-106">You initiate the file receive adapter by copying a SWIFT flat-formatted file to the inbound folder.</span></span> <span data-ttu-id="ff513-107">此操作会导致[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到出站文件夹路由有效的 SWIFT XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ff513-107">This action results in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] routing a valid SWIFT XML file to the outbound folder.</span></span>  
  
 <span data-ttu-id="ff513-108">在此任务中，您还可以提交无效的 MT103 消息。</span><span class="sxs-lookup"><span data-stu-id="ff513-108">In this task, you also submit an MT103 message that is not valid.</span></span> <span data-ttu-id="ff513-109">您可以使用事件来解决此错误。</span><span class="sxs-lookup"><span data-stu-id="ff513-109">You use the Event to resolve the error.</span></span>  
  
 <span data-ttu-id="ff513-110">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="ff513-110">This section contains:</span></span>  
  
-   [<span data-ttu-id="ff513-111">第 1 课：提交示例平面文件</span><span class="sxs-lookup"><span data-stu-id="ff513-111">Lesson 1: Submitting a Sample Flat File</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)  
  
-   [<span data-ttu-id="ff513-112">第 2 课：提交无效的 MT103 消息</span><span class="sxs-lookup"><span data-stu-id="ff513-112">Lesson 2: Submitting an MT103 Message That Is Not Valid</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-submitting-an-mt103-message-that-is-not-valid.md)  
  
-   [<span data-ttu-id="ff513-113">第 3 课：测试 XML 实例</span><span class="sxs-lookup"><span data-stu-id="ff513-113">Lesson 3: Testing an XML Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)