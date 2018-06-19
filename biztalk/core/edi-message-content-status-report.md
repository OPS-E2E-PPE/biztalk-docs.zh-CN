---
title: EDI 消息内容的状态报告 |Microsoft 文档
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
ms.openlocfilehash: 62dbb260bb23e3ed5de7e8d416158a0e142c6c32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238861"
---
# <a name="edi-message-content-status-report"></a><span data-ttu-id="27251-102">EDI 消息内容状态报表</span><span class="sxs-lookup"><span data-stu-id="27251-102">EDI Message Content Status Report</span></span>

## <a name="overview"></a><span data-ttu-id="27251-103">概述</span><span class="sxs-lookup"><span data-stu-id="27251-103">Overview</span></span>
<span data-ttu-id="27251-104">此状态报表显示的标头和负载的事务集。</span><span class="sxs-lookup"><span data-stu-id="27251-104">This status report displays the headers and payload of a transaction set.</span></span> <span data-ttu-id="27251-105">此报表显示通过右键单击事务集内设置事务的详细信息状态报表，然后单击**查看事务设置内容**。</span><span class="sxs-lookup"><span data-stu-id="27251-105">You display this report by right-clicking a transaction set within the Transaction Set Details status report, and then clicking **View Transaction Set Content**.</span></span>  
  
 <span data-ttu-id="27251-106">此报表才可用，仅当你选择**存储事务的一组负载，可用于报告**相关方的 EDI 属性对话框的常规页中的属性。</span><span class="sxs-lookup"><span data-stu-id="27251-106">This report is available only if you have selected the **Store transaction set/payload for reporting** property in the General Page of the EDI Properties dialog box for the related party.</span></span>  
  
 <span data-ttu-id="27251-107">此报表提供内容的两个视图：</span><span class="sxs-lookup"><span data-stu-id="27251-107">This report provides two views of the content:</span></span>  
  
-   <span data-ttu-id="27251-108">显示事务集在用户可读的窗体，如下所示的 EDI 文本文件的内容的文本格式视图。</span><span class="sxs-lookup"><span data-stu-id="27251-108">A Text Format view that shows the contents of the transaction set in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="27251-109">此视图显示 ST 标头，事务集负载和 SE 预告片，与在单独一行上每个段。</span><span class="sxs-lookup"><span data-stu-id="27251-109">This view shows the ST header, the transaction set payload, and the SE trailer, with each segment on a separate line.</span></span>  
  
-   <span data-ttu-id="27251-110">显示事务的内容的二进制格式视图设置非分隔的文本格式和为每个事务集内的 ASCII 字符的十六进制表示的表中。</span><span class="sxs-lookup"><span data-stu-id="27251-110">A Binary Format view that shows the contents of the transaction set in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the transaction set.</span></span>  
  
