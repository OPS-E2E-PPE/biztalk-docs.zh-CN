---
title: 安装 COM + 修补程序汇总包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 450e333503f15eec25dd7a5964223599c3928ef9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277148"
---
# <a name="installing-com-hotfix-rollup-packages"></a>安装 COM + 修补程序汇总包
> [!NOTE]  
>  本主题是仅适用于 Windows Server 2003。  
  
 应安装的最后一个版本的 Windows Server 2003 COM + 修补程序汇总包和最新版本的分布式事务处理协调器 (DTC) 汇总包。 这是因为包中包含许多性能和稳定性修复。  
  
 你应该运行的所有计算机上安装这些汇总[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和运行 SQL Server 上的所有计算机。 汇总会对您的 BizTalk 解决方案来执行在高吞吐量方案中尤其重要。  
  
 已修复的 DTC 问题如下所示：  
  
- 意外的 DTC 关闭  
  
- 内存碎片问题  
  
- DTC 可能会停止响应负载  
  
- DTC 可能会泄漏内存或停止响应时与一起使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- 改进了在负载下的 DTC 性能  
  
## <a name="installing-the-com-rollup-package"></a>安装 COM + 汇总包  
 COM + 无法再将发布汇总包。 请按照此信息来安装的最后一个的 COM + 包：  
  
-   COM + 汇总的最终版本是"Windows Server 2003 Service Pack 2 COM + 1.5年修补程序汇总包 12年"。 在任何版本的 Windows Server 2003，甚至是不带 service pack 的安装将安装此修补程序。 有关此修补程序的详细信息可在 Microsoft 知识库文章 934016， ["可用性的 Windows Server 2003 Service Pack 2 COM + 1.5年修补程序汇总包 12年"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756)。  
  
## <a name="installing-the-dtc-rollup-package"></a>安装 DTC 汇总包  
 DTC 将同时发布独立于 COM + 汇总包。 请按照此信息来安装最新的 DTC 包：  
  
-   在撰写本文时，最新的 DTC 修补程序汇总是"包 16"。 在 Microsoft 知识库文章 958013，可以找到有关此修补程序详细信息["在 Windows Server 2003 MS DTC 修补程序汇总包 16 中修复的 MS DTC 问题的列表"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919)。  
  
     可以通过搜索找到最新的 DTC 修补程序汇总包有关的 KB 文章[ http://support.microsoft.com ](http://support.microsoft.com/)短语 （包括引号）：  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     下面的查询执行此搜索。 选择最新版本：  
  
     [http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)