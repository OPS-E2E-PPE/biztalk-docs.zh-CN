---
title: 如何为 BTSTask 编辑控制台颜色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 725dcb7b-5a19-4166-9d1c-93f30ddca201
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71d902e18c851d3ae2ae432fa1e39d5db4e75206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338069"
---
# <a name="how-to-edit-the-console-colors-for-btstask"></a><span data-ttu-id="d5c7f-102">如何为 BTSTask 编辑控制台颜色</span><span class="sxs-lookup"><span data-stu-id="d5c7f-102">How to Edit the Console Colors for BTSTask</span></span>
<span data-ttu-id="d5c7f-103">本主题介绍如何编辑 BTSTask 输出到控制台的前景色。</span><span class="sxs-lookup"><span data-stu-id="d5c7f-103">This topic describes how to edit the foreground colors that BTSTask outputs to the console.</span></span> <span data-ttu-id="d5c7f-104">如果控制台背景色为白色，您将有困难查看默认 BTSTask 控制台的输出，并将需要修改控制台前景色。</span><span class="sxs-lookup"><span data-stu-id="d5c7f-104">If your console background color is white, you will have difficulty reading the default BTSTask console output and will need to modify the console foreground colors.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d5c7f-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="d5c7f-105">Prerequisites</span></span>  
 <span data-ttu-id="d5c7f-106">若要执行本主题中的过程，必须具有读/写权限中包含的 BTSTask.exe.config 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5c7f-106">To perform the procedure in this topic, you must have Read/Write permissions on the BTSTask.exe.config file contained in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder.</span></span>  
  
### <a name="to-edit-the-console-foreground-colors-for-btstask"></a><span data-ttu-id="d5c7f-107">若要为 BTSTask 编辑控制台前景色</span><span class="sxs-lookup"><span data-stu-id="d5c7f-107">To edit the console foreground colors for BTSTask</span></span>  
  
1. <span data-ttu-id="d5c7f-108">你想要运行 BTSTask 的计算机，打开中的 BTSTask.exe.config[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]或者文本或 XML 编辑器。</span><span class="sxs-lookup"><span data-stu-id="d5c7f-108">On the computer where you want to run BTSTask, open BTSTask.exe.config in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or a text or XML editor.</span></span> <span data-ttu-id="d5c7f-109">此文件位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5c7f-109">This file is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder.</span></span>  
  
2. <span data-ttu-id="d5c7f-110">编辑控制台前景色想分别要用于错误消息、 警告和信息，根据 Console.ForegroundColor.Error、 Console.ForegroundColor.Warning 和 Console.ForegroundColor.Info 项的值，然后保存文件。</span><span class="sxs-lookup"><span data-stu-id="d5c7f-110">Edit the values for the Console.ForegroundColor.Error, Console.ForegroundColor.Warning, and Console.ForegroundColor.Info keys according to the console foreground colors that you want for error messages, warnings, and information, respectively, and then save the file.</span></span> <span data-ttu-id="d5c7f-111">（对于单色，删除这三个条目，而不是无需编辑其值。）</span><span class="sxs-lookup"><span data-stu-id="d5c7f-111">(For monochrome, delete these three entries, rather than editing their values.)</span></span>  
  
    <span data-ttu-id="d5c7f-112">前景色的可用值如下所示：</span><span class="sxs-lookup"><span data-stu-id="d5c7f-112">The available values for foreground colors are as follows:</span></span>  
  
    <span data-ttu-id="d5c7f-113">0：黑色</span><span class="sxs-lookup"><span data-stu-id="d5c7f-113">0: Black</span></span>  
  
    <span data-ttu-id="d5c7f-114">1:DarkBlue</span><span class="sxs-lookup"><span data-stu-id="d5c7f-114">1: DarkBlue</span></span>  
  
    <span data-ttu-id="d5c7f-115">2:DarkGreen</span><span class="sxs-lookup"><span data-stu-id="d5c7f-115">2: DarkGreen</span></span>  
  
    <span data-ttu-id="d5c7f-116">3:DarkCyan</span><span class="sxs-lookup"><span data-stu-id="d5c7f-116">3: DarkCyan</span></span>  
  
    <span data-ttu-id="d5c7f-117">4:DarkRed</span><span class="sxs-lookup"><span data-stu-id="d5c7f-117">4: DarkRed</span></span>  
  
    <span data-ttu-id="d5c7f-118">5:DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="d5c7f-118">5: DarkMagenta</span></span>  
  
    <span data-ttu-id="d5c7f-119">6:DarkYellow</span><span class="sxs-lookup"><span data-stu-id="d5c7f-119">6: DarkYellow</span></span>  
  
    <span data-ttu-id="d5c7f-120">7:灰色</span><span class="sxs-lookup"><span data-stu-id="d5c7f-120">7: Gray</span></span>  
  
    <span data-ttu-id="d5c7f-121">8:DarkGray</span><span class="sxs-lookup"><span data-stu-id="d5c7f-121">8: DarkGray</span></span>  
  
    <span data-ttu-id="d5c7f-122">9:蓝色</span><span class="sxs-lookup"><span data-stu-id="d5c7f-122">9: Blue</span></span>  
  
    <span data-ttu-id="d5c7f-123">10:绿色</span><span class="sxs-lookup"><span data-stu-id="d5c7f-123">10: Green</span></span>  
  
    <span data-ttu-id="d5c7f-124">11:蓝绿色</span><span class="sxs-lookup"><span data-stu-id="d5c7f-124">11: Cyan</span></span>  
  
    <span data-ttu-id="d5c7f-125">12:Red</span><span class="sxs-lookup"><span data-stu-id="d5c7f-125">12: Red</span></span>  
  
    <span data-ttu-id="d5c7f-126">13:洋红色</span><span class="sxs-lookup"><span data-stu-id="d5c7f-126">13: Magenta</span></span>  
  
    <span data-ttu-id="d5c7f-127">14:Yellow</span><span class="sxs-lookup"><span data-stu-id="d5c7f-127">14: Yellow</span></span>  
  
    <span data-ttu-id="d5c7f-128">15:白色</span><span class="sxs-lookup"><span data-stu-id="d5c7f-128">15: White</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c7f-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5c7f-129">See Also</span></span>  
 [<span data-ttu-id="d5c7f-130">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="d5c7f-130">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)