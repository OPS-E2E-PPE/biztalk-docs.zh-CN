---
title: 第 2 课：提交无效的 MT103 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, invalid messages
- submitting, invalid messages
- submitting, MT103 messages
- MT103 messages
- messages, MT103 messages
ms.assetid: 4b070ae1-c400-421a-b2f6-b7b1f22c0e41
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b686b0ba84d5069f739f129495ee14c7654645d8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530336"
---
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="73d85-102">第 2 课：提交无效的 MT103 消息</span><span class="sxs-lookup"><span data-stu-id="73d85-102">Lesson 2: Submitting an MT103 Message That Is Not Valid</span></span>
<span data-ttu-id="73d85-103">在本课中，提交是无效的 MT103 消息并您解决在使用系统工具所生成的错误。</span><span class="sxs-lookup"><span data-stu-id="73d85-103">In this lesson, you submit an MT103 message that is not valid and then you troubleshoot the resulting error using your System Tools.</span></span>  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="73d85-104">若要提交无效的 MT103 消息</span><span class="sxs-lookup"><span data-stu-id="73d85-104">To submit an MT103 message that is not valid</span></span>  
  
1. <span data-ttu-id="73d85-105">将文件 MT103_Invalid_Sample.txt 复制从\<*驱动器：*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial 到\<*驱动器*\>: \Labs\Inbound\FlatFile 文件夹。</span><span class="sxs-lookup"><span data-stu-id="73d85-105">Copy the file MT103_Invalid_Sample.txt from \<*drive:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial to \<*drive*\>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="73d85-106">请注意该文件放到文件夹的时间。</span><span class="sxs-lookup"><span data-stu-id="73d85-106">Note the time that you drop the file into the folder.</span></span>  
  
2. <span data-ttu-id="73d85-107">打开\<*驱动器：*\>\Labs\Outbound 验证对应于 MT103_Invalid_Sample.txt 任何 XML 文件是否在文件夹中。</span><span class="sxs-lookup"><span data-stu-id="73d85-107">Open \<*drive:*\>\Labs\Outbound to verify that no XML file corresponding to MT103_Invalid_Sample.txt is in the folder.</span></span> <span data-ttu-id="73d85-108">（对应于有效的 MT103_Sample.txt 消息的 XML 文件仍应在该文件夹中。）</span><span class="sxs-lookup"><span data-stu-id="73d85-108">(The XML file corresponding to the valid MT103_Sample.txt message should still be in that folder.)</span></span>  
  
3. <span data-ttu-id="73d85-109">在记事本中，打开文件 MT103_Invalid_Sample.txt 中\<*驱动器：*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial。</span><span class="sxs-lookup"><span data-stu-id="73d85-109">In Notepad, open the file MT103_Invalid_Sample.txt in \<*drive:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial.</span></span>  
  
4. <span data-ttu-id="73d85-110">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="73d85-110">Start **BizTalk Server Administration**.</span></span>  
  
5. <span data-ttu-id="73d85-111">在 BizTalk Server 管理控制台中，展开**事件查看器 （本地）**，然后单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="73d85-111">In the BizTalk Server Administration Console, expand **Event Viewer (Local)**, and then click **Application**.</span></span>  
  
6. <span data-ttu-id="73d85-112">查找具有的源 BizTalk Accelerator for SWIFT 和放置到无效的消息时，对应于时间的错误条目\<*驱动器*\>: \Labs\Inbound\FlatFile 文件夹。</span><span class="sxs-lookup"><span data-stu-id="73d85-112">Look for an error entry that has a source of BizTalk Accelerator for SWIFT and a time that corresponds to when you dropped the invalid message into the \<*drive*\>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="73d85-113">双击该错误条目。</span><span class="sxs-lookup"><span data-stu-id="73d85-113">Double-click that error entry.</span></span>  
  
7. <span data-ttu-id="73d85-114">在错误事件属性对话框中，验证说明窗格中，失败的消息已发布到 MessageBox SWIFT 反汇编程序标记为**A4SWIFT_Failed**作为**True**。</span><span class="sxs-lookup"><span data-stu-id="73d85-114">In the Event Properties dialog box for the error, verify in the Description pane that the failed message was published to the MessageBox and that the SWIFT Disassembler marked **A4SWIFT_Failed** as **True**.</span></span> <span data-ttu-id="73d85-115">关闭事件属性对话框。</span><span class="sxs-lookup"><span data-stu-id="73d85-115">Close the Event Properties dialog box.</span></span>  
  
8. <span data-ttu-id="73d85-116">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="73d85-116">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, and then expand **BizTalk Group**.</span></span> <span data-ttu-id="73d85-117">在中**视图**菜单上，单击**组中心页**。</span><span class="sxs-lookup"><span data-stu-id="73d85-117">In the **View** menu, click **Group Hub Page**.</span></span>  
  
9. <span data-ttu-id="73d85-118">在中**组概述**窗格中，在**分组的挂起服务实例**窗格中，单击**应用程序分组存放**。</span><span class="sxs-lookup"><span data-stu-id="73d85-118">In the **Group Overview** pane, in the **Grouped Suspended Service Instances** pane, click **Grouped by Application**.</span></span>  
  
10. <span data-ttu-id="73d85-119">在中**为所选的查询结果的预览**窗格中，双击条目**MT103_FlatFile_ReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="73d85-119">In the **Preview for the selected query result** pane, double-click the entry for **MT103_FlatFile_ReceivePort**.</span></span>  
  
11. <span data-ttu-id="73d85-120">在服务详细信息对话框中，单击**消息**选项卡。双击服务名称是为其条目**MT103_FlatFile_ReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="73d85-120">In the Service Details dialog box, click the **Messages** tab. Double-click the entry for which the Service Name is **MT103_FlatFile_ReceivePort**.</span></span>  
  
12. <span data-ttu-id="73d85-121">在消息详细信息对话框中，单击**正文**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="73d85-121">In the Message Details dialog box, click **Body** in the left pane.</span></span>  
  
13. <span data-ttu-id="73d85-122">验证消息详细信息对话框中的正文窗格中显示该消息对应于 MT103_Invalid_Sample.txt 在记事本中打开。</span><span class="sxs-lookup"><span data-stu-id="73d85-122">Verify that the message displayed in the body pane of the Message Details dialog box corresponds to MT103_Invalid_Sample.txt that you opened in Notepad.</span></span>  
  
    <span data-ttu-id="73d85-123">请继续执行[第 3 课：测试 XML 实例](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="73d85-123">Proceed to [Lesson 3: Testing an XML Instance](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md).</span></span>