---
title: EDI 消息内容状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29acab25-354d-42f0-b6e3-37ebca47addb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cdda1a3188809d9209d8acb2badc4c035724706
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350431"
---
# <a name="edi-message-content-status-report"></a><span data-ttu-id="1c0b2-102">EDI 消息内容状态报告</span><span class="sxs-lookup"><span data-stu-id="1c0b2-102">EDI Message Content Status Report</span></span>

## <a name="overview"></a><span data-ttu-id="1c0b2-103">概述</span><span class="sxs-lookup"><span data-stu-id="1c0b2-103">Overview</span></span>
<span data-ttu-id="1c0b2-104">此状态报告中显示的标头和负载的事务集。</span><span class="sxs-lookup"><span data-stu-id="1c0b2-104">This status report displays the headers and payload of a transaction set.</span></span> <span data-ttu-id="1c0b2-105">通过右键单击事务集内事务集详细信息状态报告中，然后单击显示此报告**查看事务集内容**。</span><span class="sxs-lookup"><span data-stu-id="1c0b2-105">You display this report by right-clicking a transaction set within the Transaction Set Details status report, and then clicking **View Transaction Set Content**.</span></span>  
  
 <span data-ttu-id="1c0b2-106">此报表才可用，仅当你选择**存储事务集/负载以用于报告**相关参与方 EDI 属性对话框的常规页中的属性。</span><span class="sxs-lookup"><span data-stu-id="1c0b2-106">This report is available only if you have selected the **Store transaction set/payload for reporting** property in the General Page of the EDI Properties dialog box for the related party.</span></span>  
  
 <span data-ttu-id="1c0b2-107">此报表提供了两个视图的内容：</span><span class="sxs-lookup"><span data-stu-id="1c0b2-107">This report provides two views of the content:</span></span>  
  
-   <span data-ttu-id="1c0b2-108">显示用户可读的窗体，如下所示 EDI 文本文件中的事务集的内容的文本格式视图。</span><span class="sxs-lookup"><span data-stu-id="1c0b2-108">A Text Format view that shows the contents of the transaction set in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="1c0b2-109">此视图显示 ST 标头，事务集有效负载和 SE 尾部，每个分段都位于单独的一行。</span><span class="sxs-lookup"><span data-stu-id="1c0b2-109">This view shows the ST header, the transaction set payload, and the SE trailer, with each segment on a separate line.</span></span>  
  
-   <span data-ttu-id="1c0b2-110">显示事务的内容的二进制格式视图设置以非分隔文本格式和事务集中的每个 ASCII 字符的十六进制表示形式的表。</span><span class="sxs-lookup"><span data-stu-id="1c0b2-110">A Binary Format view that shows the contents of the transaction set in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the transaction set.</span></span>  
  
