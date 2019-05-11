---
title: 分布式系统问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 287b0adb-d5f9-4e47-80f8-0ba5d90c7864
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674af4da96fe62c4955ea93af5c2026f850dafe6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305710"
---
# <a name="distributed-system-problems"></a>分布式的系统难题
在分布式的目标系统的还原作业不了解的错误或其他计算机上的问题。 例如，假设计算机 A 还原的 BizTalk 管理数据库和 BizTalk 跟踪数据库中，并且计算机 B 正在还原的 BizTalk MessageBox 数据库。 这两台计算机已成功还原备份集 1 到 25。 集 26，但是，具有 BizTalk MessageBox 数据库的损坏的日志备份文件。 计算机 A 正确还原其数据库，但计算机 B 无法还原损坏的文件。  
  
 在此情况下，强制执行源系统上的完整备份。 继续上面的示例，假定已诊断问题并为集 35 创建完整备份。 计算机 A 然后还原集 26 到 34，因为它不是意识到这个问题在计算机 b。 计算机 B 上将失败直到它看到完整备份集 35 和后续日志备份集 （请记住，即必须始终会为一组的一个后续完成日志备份要还原的 36 为止d) 中。 当集 35 和 36 计算机 B 上，它会修复本身使用 35。 修复完成后，会同步计算机 A 和 B。  
  
## <a name="see-also"></a>请参阅  
 [日志传送疑难解答](../technical-guides/troubleshooting-log-shipping.md)