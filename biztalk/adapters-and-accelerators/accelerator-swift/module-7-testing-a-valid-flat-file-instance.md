---
title: "模块 7： 测试的有效的平面文件实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, flat file instance
- tutorial, testing flat file instance
- flat files, testing
ms.assetid: ba8a5d81-41b0-4da7-8c2e-02cf29953af7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 572df71fe479bc26e6b803cdbb95ff7a409c394a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="module-7-testing-a-valid-flat-file-instance"></a><span data-ttu-id="9a4a7-102">模块 7： 测试的有效的平面文件实例</span><span class="sxs-lookup"><span data-stu-id="9a4a7-102">Module 7: Testing a Valid Flat File Instance</span></span>
<span data-ttu-id="9a4a7-103">在此模块中，你可以提交有效示例 MT103 平面文件的文件接收在以前的实验室中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="9a4a7-103">In this module, you submit a valid sample MT103 flat file to the file receive ports created in the previous labs.</span></span> <span data-ttu-id="9a4a7-104">此任务用于测试接收管道在以前的实验室中创建。</span><span class="sxs-lookup"><span data-stu-id="9a4a7-104">This task tests the receive pipelines you created in previous labs.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="9a4a7-105">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]将 XML 格式的输出写入到你在上一课中，所选发送端口中的输出文件夹[第 2 课： 添加 XML 发送端口](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="9a4a7-105">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] writes the output in XML format to the output folder in the send port you selected in the previous lesson, [Lesson 2: Adding an XML Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span></span>  
  
 <span data-ttu-id="9a4a7-106">启动文件通过将 SWIFT 的平面格式的文件复制到入站文件夹接收适配器。</span><span class="sxs-lookup"><span data-stu-id="9a4a7-106">You initiate the file receive adapter by copying a SWIFT flat-formatted file to the inbound folder.</span></span> <span data-ttu-id="9a4a7-107">此操作会导致[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]路由到的出站文件夹的有效 SWIFT XML 文件。</span><span class="sxs-lookup"><span data-stu-id="9a4a7-107">This action results in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] routing a valid SWIFT XML file to the outbound folder.</span></span>  
  
 <span data-ttu-id="9a4a7-108">在此任务中，您还可以提交一条 MT103 消息无效。</span><span class="sxs-lookup"><span data-stu-id="9a4a7-108">In this task, you also submit an MT103 message that is not valid.</span></span> <span data-ttu-id="9a4a7-109">事件用于解决该错误。</span><span class="sxs-lookup"><span data-stu-id="9a4a7-109">You use the Event to resolve the error.</span></span>  
  
 <span data-ttu-id="9a4a7-110">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="9a4a7-110">This section contains:</span></span>  
  
-   [<span data-ttu-id="9a4a7-111">第 1 课： 提交示例平面文件</span><span class="sxs-lookup"><span data-stu-id="9a4a7-111">Lesson 1: Submitting a Sample Flat File</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)  
  
-   [<span data-ttu-id="9a4a7-112">第 2 课： 提交无效 MT103 消息</span><span class="sxs-lookup"><span data-stu-id="9a4a7-112">Lesson 2: Submitting an MT103 Message That Is Not Valid</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-submitting-an-mt103-message-that-is-not-valid.md)  
  
-   [<span data-ttu-id="9a4a7-113">第 3 课： 测试 XML 实例</span><span class="sxs-lookup"><span data-stu-id="9a4a7-113">Lesson 3: Testing an XML Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)