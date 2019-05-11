---
title: 确定列是否存储小写或大写值 |Microsoft Docs
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
ms.openlocfilehash: 9a457ddbde4a6a1dcfa3b4d2c4f818d01dcae009
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373528"
---
# <a name="determining-whether-a-column-stores-lowercase-or-uppercase-values"></a>确定列存储小写或大写值
本部分列出了要在 SAP 系统，以确定是否 SAP 表中的列存储小写或大写字符上执行的高级任务。 有关详细说明如何执行此任务必须与 SAP 管理员联系或，请参阅 SAP 文档。  
  
### <a name="to-determine-the-case-of-values-stored-in-a-column"></a>若要确定在列中存储的值的用例  
  
1.  启动将 SAP GUI。  
  
2.  转到事务 SE37 并执行 DDIF_TABL_GET。  
  
3.  为 NAME 参数指定包含你想要确定字符大小写信息的列的表的名称。 例如，KNA1。  
  
4.  第一个表参数是 DD03P_TAB。 单击以查看表中的行的参数。 此表中的每一行对应一列 （如 KNA1) 表中您指定在步骤 3 中。  
  
5.  在 DD03P_TAB，查找每个行的小写形式的列中的值。 如果小写列中的值为 X，（例如 KNA1)，表中的相应列可以存储小写和大写字符。 如果小写列中的值为空，相应的列只能存储大写字符。  
  
     例如，对于名称行小写字母列是 X。因此，KNA1 中的名称列可以存储大写和小写字符。 但是，对于 LAND1 行小写字母列为空。 因此，KNA1 表中的 LAND1 列只能存储大写字符。  
  
## <a name="see-also"></a>请参阅  
 [特定的 SAP 适配器方案中使用 SAP GUI 执行任务](../../adapters-and-accelerators/adapter-sap/performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)