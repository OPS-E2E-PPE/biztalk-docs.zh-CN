---
title: 第 3 课： 测试 XML 实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, XML instances
- XML instances
ms.assetid: 19d7dd18-17dc-4355-a4f1-5c5e6750faf3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5660ab4e67545b1b98785aedeaeea6e123b6d008
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971894"
---
# <a name="lesson-3-testing-an-xml-instance"></a><span data-ttu-id="4b81c-102">第 3 课： 测试 XML 实例</span><span class="sxs-lookup"><span data-stu-id="4b81c-102">Lesson 3: Testing an XML Instance</span></span>
<span data-ttu-id="4b81c-103">在本课中，你提交无效的 MT103 消息采用 XML 格式的文件接收端口创建在前面的课程。</span><span class="sxs-lookup"><span data-stu-id="4b81c-103">In this lesson, you submit a valid MT103 message in XML format to the file receive ports created in the previous lessons.</span></span> <span data-ttu-id="4b81c-104">此操作测试你在上一模块中创建的发送管道。</span><span class="sxs-lookup"><span data-stu-id="4b81c-104">This action tests the send pipelines that you created in previous modules.</span></span> <span data-ttu-id="4b81c-105">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]以平面文件输出写入为前一模块中的发送端口选择的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="4b81c-105">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] writes the output as a flat file to the output folder that you selected for the send port in the previous module.</span></span>  
  
 <span data-ttu-id="4b81c-106">启动文件接收适配器的将 SWIFT XML 格式的文件复制到入站的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4b81c-106">You initiate the file receive adapter by copying a SWIFT XML-formatted file to the inbound folder.</span></span> <span data-ttu-id="4b81c-107">此操作会导致系统将有效的 SWIFT 平面文件复制到出站的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4b81c-107">This action results in the system copying a valid SWIFT flat file to the outbound folder.</span></span>  
  
### <a name="to-test-an-xml-instance"></a><span data-ttu-id="4b81c-108">若要测试 XML 实例</span><span class="sxs-lookup"><span data-stu-id="4b81c-108">To test an XML Instance</span></span>  
  
1. <span data-ttu-id="4b81c-109">在 Windows 资源管理器中打开\<*驱动器*\>: \Labs\Outbound。</span><span class="sxs-lookup"><span data-stu-id="4b81c-109">In Windows Explorer, open \<*drive*\>:\Labs\Outbound.</span></span> <span data-ttu-id="4b81c-110">验证此文件夹包含发送到此文件夹中的 {GUID}.xml 文件[第 1 课： 提交示例平面文件](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)此模块。</span><span class="sxs-lookup"><span data-stu-id="4b81c-110">Verify that this folder contains the {GUID}.xml file that you sent to this folder in [Lesson 1: Submitting a Sample Flat File](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md) of this module.</span></span>  
  
2. <span data-ttu-id="4b81c-111">复制 XML 文件中，并将其粘贴到\<*驱动器*\>: \Labs\Inbound\XMLFile。</span><span class="sxs-lookup"><span data-stu-id="4b81c-111">Copy the XML file, and paste it into \<*drive*\>:\Labs\Inbound\XMLFile.</span></span> <span data-ttu-id="4b81c-112">请注意在粘贴此文件的时间。</span><span class="sxs-lookup"><span data-stu-id="4b81c-112">Note the time that you pasted this file.</span></span>  
  
3. <span data-ttu-id="4b81c-113">将移动到\<*驱动器*\>: \Labs\Outbound。</span><span class="sxs-lookup"><span data-stu-id="4b81c-113">Move to \<*drive*\>:\Labs\Outbound.</span></span> <span data-ttu-id="4b81c-114">验证是否在此文件夹中，名为 {GUID}.txt 的文件，以及此文件修改日期列中的时间对应于粘贴到文件的时间\<*驱动器*\>: \Labs\Inbound\XMLFile。</span><span class="sxs-lookup"><span data-stu-id="4b81c-114">Verify that there is a file called {GUID}.txt in this folder, and that the time in the Date Modified column for this file corresponds to the time that you pasted the file into \<*drive*\>:\Labs\Inbound\XMLFile.</span></span>  
  
4. <span data-ttu-id="4b81c-115">在记事本中，打开在 MT103_Sample.txt \<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial。</span><span class="sxs-lookup"><span data-stu-id="4b81c-115">In Notepad, open MT103_Sample.txt in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial.</span></span>  
  
5. <span data-ttu-id="4b81c-116">在记事本的另一个实例中，打开中的 {GUID}.txt \<*驱动器*\>: \Labs\Inbound\XMLFile。</span><span class="sxs-lookup"><span data-stu-id="4b81c-116">In another instance of Notepad, open {GUID}.txt in \<*drive*\>:\Labs\Inbound\XMLFile.</span></span>  
  
6. <span data-ttu-id="4b81c-117">验证在记事本中的两个文件包含相同的内容。</span><span class="sxs-lookup"><span data-stu-id="4b81c-117">Verify that the two files in Notepad contain the same content.</span></span>  
  
   <span data-ttu-id="4b81c-118">请继续执行[模块 8： 修复无效消息](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d)。</span><span class="sxs-lookup"><span data-stu-id="4b81c-118">Proceed to [Module 8: Repairing an Invalid Message](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d).</span></span>