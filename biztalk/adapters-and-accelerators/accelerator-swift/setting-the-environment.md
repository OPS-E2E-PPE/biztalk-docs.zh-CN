---
title: "将环境设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43027efc-acec-4110-96bd-cc4a19daaeab
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c91221162cccb7b6821c0edad12f8e76de2f10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-environment"></a>将环境设置
**若要将环境设置：**  
  
1.  请确保配置 SWIFT 消息包。 请参阅 Swift 消息包文档配置相同。  
  
2.  运行 SQL 脚本*\<驱动器 >*: files\microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql。 如果为 A4Swift 之外的数据库名称配置了 Swift 和 MessagePack，更改中的 sql 脚本的数据库名称。  
  
3.  将键"数据源"的值设置为计算机名和密钥"数据库"作为数据库名称 (为其配置的 Swift 和 MessagePack) 文件中*\<驱动器 >*: files\microsoft BizTalk Accelerator 为SWIFT\SDK\Tools\DataImport\DataImport.exe.config。  
  
    > [!NOTE]
    >  数据输入的文件不应在 DataImport.exe 文件所在的同一文件夹中。  
  
4.  运行数据导入实用程序导入 BICplusIBAN 和 SEPA 表中的数据。