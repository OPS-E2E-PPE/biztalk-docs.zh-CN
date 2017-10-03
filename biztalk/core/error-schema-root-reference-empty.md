---
title: "错误-架构根引用为空 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.rootRefEmpty
ms.assetid: 172e6ad8-6118-40db-9451-92808a3a2051
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7217f6f9ea328aff4864cfdf3bee9ea71de3741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-root-reference-empty"></a>错误-架构根引用为空
**错误代码**  
  
 BEC2005  
  
 **说明**  
  
 **根引用**属性**架构**未设置节点。 当**标准**属性**架构**节点设置为值**XML**，必须设置**根引用**属性指示子节点**架构**旨在用作此架构定义的消息的根节点。  
  
 **用户执行任何操作**  
  
 根据您的架构的具体情况，请设置**标准**属性**架构**节点**XML**，或设置**根引用**属性**架构**到适当的子节点的节点**架构**节点。 这些子节点位于**根引用**属性下拉列表。