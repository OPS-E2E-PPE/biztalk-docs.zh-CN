---
title: SQL 适配器示例的工作原理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77811152-cc8e-4090-89eb-e3a402a46e5e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ff56f2f2f88d35290ffd897d107910e206ac98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294005"
---
# <a name="how-the-sql-adapter-sample-works"></a>SQL 适配器示例的工作原理
SQL 适配器示例提供了使用路由服务和转换消息服务配置示例双向路线。  
  
 路由服务配置了静态冲突解决程序，指定应将消息路由执行名为 InsertProduct 使用 WCF 自定义适配器提供程序的 GlobalBankESB 数据库内的一个 SQL 存储过程。  
  
 转换服务指定的地图，将传入消息转换为 InsertProduct 存储过程接受的格式。