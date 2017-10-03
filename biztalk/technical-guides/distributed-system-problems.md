---
title: "分布式系统问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 287b0adb-d5f9-4e47-80f8-0ba5d90c7864
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24abe471a66e8bc0724ad731388c5a0e7c07b573
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="distributed-system-problems"></a>分布式的系统问题
分布式的目标系统中的还原作业不知道的错误或其他计算机上的问题。 例如，假设计算机 A 正在还原 BizTalk 管理数据库和 BizTalk 跟踪数据库，并且计算机 B 正在还原的 BizTalk MessageBox 数据库。 这两台计算机成功还原备份集 1 到 25。 集 26，但是，具有 BizTalk MessageBox 数据库的损坏的日志备份文件。 计算机 A 正确还原其数据库，但计算机 B 无法还原损坏的文件。  
  
 在此情况下，强制源系统上的完整备份。 继续上面的示例，假定已诊断问题并为集 35 创建完整备份。 计算机 A 然后还原集 26 到 34，因为它并不知道的计算机。 计算机 B 上的问题将失败直到它看到完整备份集 35 和后续日志备份集 （请记住： 必须始终为一组的一个完整的后续日志备份还原的 36d)。 当集 35 和 36 到达计算机 B 上时，它将修复本身使用 35。 完成修复后，将同步计算机 A 和 B。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除日志传送](../technical-guides/troubleshooting-log-shipping.md)