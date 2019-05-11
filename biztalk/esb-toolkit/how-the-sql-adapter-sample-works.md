---
title: SQL 适配器示例的工作原理 |Microsoft Docs
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
ms.openlocfilehash: 4e59df235628539786917d7aa483e23a18d7c87c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279065"
---
# <a name="how-the-sql-adapter-sample-works"></a>SQL 适配器示例的工作原理
SQL 适配器示例提供了使用路由服务和转换消息传送服务配置示例双向路线。  
  
 路由服务配置为静态解析程序，它指定应将消息路由执行名为 InsertProduct 使用 WCF 自定义适配器提供程序的 GlobalBankESB 数据库内的一个 SQL 存储过程。  
  
 转换服务指定一个映射，以将传入消息转换为 InsertProduct 存储过程接受的格式。