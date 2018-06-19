---
title: 确定列是否存储小写或大写值 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1edc8332-d8c7-4040-895b-f121fb03df44
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b54c00b43192462fb095dbfbfda4cbf0b248a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216981"
---
# <a name="determining-whether-a-column-stores-lowercase-or-uppercase-values"></a>确定是否列存储小写或大写值
本部分列出在 SAP 系统，以确定是否 SAP 表中的列存储小写或大写字符上执行的高级任务。 有关如何执行此任务的详细说明必须联系您的 SAP 管理员，或请参阅 SAP 文档。  
  
### <a name="to-determine-the-case-of-values-stored-in-a-column"></a>若要确定存储在列的值的大小写  
  
1.  启动 SAP GUI。  
  
2.  转到事务 SE37 并执行 DDIF_TABL_GET。  
  
3.  为名称参数指定包含你想要确定字符大小写信息的列的表的名称。 例如，KNA1。  
  
4.  第一个表参数是 DD03P_TAB。 单击以查看表中的行的参数。 此表中的每行对应于的列 （如 KNA1) 表中你在步骤 3 中指定。  
  
5.  在 DD03P_TAB，查找每个行的小写列中的值。 如果小写列中的值是 X，（例如 KNA1)，表中的相应列可以存储小写和大写字母字符。 如果小写列中的值为空，相应的列可以仅存储大写字符。  
  
     例如，对于名称行小写列是 X。因此，KNA1 中的名称列可以存储大写和小写字符。 但是，对于 LAND1 行小写列是空的。 因此，KNA1 表中的 LAND1 列可以仅存储大写字符。  
  
## <a name="see-also"></a>另请参阅  
 [对于特定 SAP 适配器方案中使用 SAP GUI 执行任务](../../adapters-and-accelerators/adapter-sap/performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)