---
title: "Edifact 交换应具有包含 TransactionSetGroup 或 FunctionalGroup Xml 标记 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34318133-211f-422d-acdf-b841ece5d2b0
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adb93582daf235a7f1f0633231e536f3c5b14ab0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-interchange-should-have-contained-transactionsetgroup-or-functionalgroup-xml-tags"></a>Edifact 交换应该包含 TransactionSetGroup 或 FunctionalGroup Xml 标记
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|Edifact 交换应该包含 TransactionSetGroup 或 FunctionalGroup Xml 标记|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理保留的 EDIFACT 批处理交换，因为该交换的 XML 文件中不包含 TransactionSetGroup 或 FunctionalGroup 标记。  
  
 当 BizTalk 处理保留的批处理交换时，为该交换的 XML 文件中的一组事务集或组给出了 XML 标记。 为一组事务集给出了 TransactionSetGroup 标记。 为一组组给出了 FunctionalGroup 标记。 如果您使用接收管道和直通传输发送管道设置保留的批处理，则可能会出现此错误条件。 这些标记是由接收管道设置的并且由发送管道删除。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保为保留的批处理器生成的 XML 文件具有格式正确的 XML 结构，该结构具有 TransactionSetGroup 标记（对于一个具有多个事务集的组） 和/或 FunctionalGroup 标记（对于多个组）。