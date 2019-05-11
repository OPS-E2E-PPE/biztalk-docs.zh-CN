---
title: 错误-架构依存关系无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.schemaDependencyNotValid
ms.assetid: 431278f0-6cd1-4b3f-8d87-16af4991d354
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcee29e7074ca012c11aea738c5fa44c6e702352
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346956"
---
# <a name="error---schema-dependency-not-valid"></a>错误-架构依存关系无效
**错误代码**  
  
 BEC2009  
  
 **说明**  
  
 所有相关的架构，如将导入的那些包含，或当前架构中重新定义，必须添加到此 BizTalk 项目或存在于此项目所引用的程序集。 即使架构**导入**，**包括**，并**重新定义**必须将架构指定远程网站的指令添加到此 BizTalk 项目。  
  
 **用户执行任何操作**  
  
 使用**添加现有项**命令**文件**菜单和 Microsoft® BizTalk® Server 项目将此架构所依赖的所有架构添加到 BizTalk 项目的快捷菜单。 您可能需要此类架构从 Web 站点下载到本地硬盘之前将它们添加到 BizTalk 项目。