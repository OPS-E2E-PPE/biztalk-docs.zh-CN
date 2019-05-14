---
title: 设置环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43027efc-acec-4110-96bd-cc4a19daaeab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2bcff19cb26482c566820956f93642887b43015
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530101"
---
# <a name="setting-the-environment"></a>设置环境
**若要设置的环境：**  
  
1.  请确保配置 SWIFT 消息程序包。 请参阅 Swift 消息包文档配置相同。  
  
2.  运行 SQL 脚本*\<驱动器\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql。 如果 Swift 和 MessagePack 配置 A4Swift 以外的数据库名称，请更改 sql 脚本中的数据库名称。  
  
3.  将关键字"数据源"的值设置为计算机名和密钥作为数据库名称的"数据库"(为其配置 Swift 和 MessagePack) 文件中*\<驱动器\>*: \Program Files\Microsoft BizTalkAccelerator for SWIFT\SDK\Tools\DataImport\DataImport.exe.config。  
  
    > [!NOTE]
    >  数据输入的文件不应在 DataImport.exe 文件所在的同一文件夹中。  
  
4.  运行数据导入实用工具，以导入 BICplusIBAN 和 SEPA 表中的数据。