---
title: 安装 COM + 修补程序汇总包 |Microsoft 文档
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
ms.openlocfilehash: 40610c649e00993323adedf0ea29330dd289a0e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298405"
---
# <a name="installing-com-hotfix-rollup-packages"></a>安装 COM + 修补程序汇总包
> [!NOTE]  
>  本主题是仅适用于 Windows Server 2003。  
  
 你应安装了上一版本的 Windows Server 2003 COM + 修补程序汇总包和最新版本的分布式事务处理协调器 (DTC) 汇总包。 这是因为包中包含许多性能和稳定性的修补程序。  
  
 应运行的所有计算机上安装这些汇总[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和运行 SQL Server 上的所有计算机。 汇总尤其是对于非常重要 BizTalk 解决方案以高吞吐量方案中良好地执行。  
  
 已修复的 DTC 问题如下所示：  
  
-   意外的 DTC 关闭  
  
-   内存碎片问题  
  
-   DTC 可能会停止在负载下作出响应  
  
-   DTC 可能会泄漏内存或停止响应一起使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   DTC 负载的性能已改进  
  
## <a name="installing-the-com-rollup-package"></a>安装 COM + 汇总包  
 COM + 不再释放汇总包。 请按照此信息来安装的最后一个的 COM + 包：  
  
-   COM + 汇总的最终版本是"Windows Server 2003 Post-service Pack 2 COM + 1.5年修补程序汇总包 12年"。 此修补程序将安装在 Windows Server 2003，甚至那些不带 service pack 安装的任何版本上。 有关此修补程序的详细信息可在 Microsoft 知识库文章 934016， ["可用性的 Windows Server 2003 Post-service Pack 2 COM + 1.5年修补程序汇总包 12年"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756)。  
  
## <a name="installing-the-dtc-rollup-package"></a>安装 DTC 汇总包  
 DTC 即将发布的 COM + 独立汇总包。 请遵循此信息来安装最新的 DTC 包：  
  
-   截至撰写本文时，最新的 DTC 修补程序汇总为"包 16"。 有关此修补程序的详细信息可在 Microsoft 知识库文章 958013， ["List of Windows Server 2003 MS DTC 修补程序汇总包 16 中修复的 MS DTC 问题"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).  
  
     可以通过搜索找到有关最新的 DTC 修补程序汇总包的 KB 文章[http://support.microsoft.com](http://support.microsoft.com/)短语 （包括引号）：  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     下面的查询执行此搜索。 选择的最新项目：  
  
     [http://support.microsoft.com/search/default.aspx?query="MS + DTC + 修补程序 + 汇总 + 包"](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)