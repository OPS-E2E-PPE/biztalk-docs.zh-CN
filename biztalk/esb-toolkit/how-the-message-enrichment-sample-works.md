---
title: "消息扩充示例的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1188c1c9-b133-4438-b41c-ea6cffcf40fd
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ef516b992acbcee2936edb6341cbf1434ba4c79
ms.sourcegitcommit: 7497f6f23d7aadfa8535d0530493f8b4a2a50a0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
# <a name="how-the-message-enrichment-sample-works"></a>消息扩充示例的工作原理
 消息扩充示例演示可以封装作为泛型的可重用服务的集成模式。 在这种情况下，此示例实现内容 Enricher 模式。 内容 Enricher 模式通常涉及使用转换准备一条消息以发送给顺序查找信息，到外部服务，并将另一个转换以将响应合并到一条新消息还包含中的数据原始消息。 为通用的方式实现的模式，消息扩充示例提供了一种可以使用最多两个冲突解决程序来配置使用从外部源的信息的消息的扩充基于业务流程的路线服务。
  
 第一个冲突解决程序必须返回路由信息;它还可以返回转换在其旁边的信息。 如果指定，路由之前应用到传入消息转换到由解析程序指定的位置。 在提供的示例路线，WCF 自定义适配器提供程序用于执行名为 GetOrderDetails GlobalBankESB 数据库内的一个 SQL 存储过程并返回结果。  
  
 （可选） 可以包含第二个冲突解决程序。 如果提供，第二个解析程序必须包括转换信息。 将给定此转换，原始消息和返回任何数据源已连接，作为输入的结果。 在示例路线中被引用使用循环 functoid 表中提取出原始消息和存储过程的结果的信息并将其包含在生成的 InventoryOrder 消息映射。
