---
title: 错误-架构根引用为空 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.rootRefEmpty
ms.assetid: 172e6ad8-6118-40db-9451-92808a3a2051
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c56119e88948211f7b2e93add1d6e23d08e1b9fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346885"
---
# <a name="error---schema-root-reference-empty"></a>错误-架构根引用为空
**错误代码**  
  
 BEC2005  
  
 **说明**  
  
 **根引用**的属性**架构**未设置节点。 当**标准**的属性**架构**节点设置为值**XML**，则必须设置**根引用**属性设置为指示的哪个子节点**架构**旨在用作此架构所定义的消息的根节点。  
  
 **用户执行任何操作**  
  
 根据您的架构的具体情况，请设置**标准**的属性**架构**节点**XML**，或设置**根引用**属性的**架构**对其相应的子节点的节点**架构**节点。 这些子节点是中提供**根引用**属性下拉列表。