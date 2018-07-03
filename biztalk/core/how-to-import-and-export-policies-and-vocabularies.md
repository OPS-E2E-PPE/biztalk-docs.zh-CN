---
title: 如何导入和导出策略及词汇 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- Rule Engine Deployment Wizard
- policies, importing
- vocabularies, exporting
- vocabularies, importing
ms.assetid: c427f686-5908-4f72-9e72-46a5497274ac
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bb235d126ca775cc8bd5a752388c948a2203e4b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968838"
---
# <a name="how-to-import-and-export-policies-and-vocabularies"></a>如何导入和导出策略及词汇
可以使用规则引擎部署向导导入或导出策略或词汇。  

> [!NOTE]
>  必须首先导入策略或词汇使用的所有词汇，否则将出现错误。  

### <a name="to-import-or-export-a-policy-or-vocabulary"></a>导入或导出策略或词汇  

1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则引擎部署向导**。  

   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  

2. 在欢迎页上，单击**下一步**。  

3. 上**部署任务**页上，选择**策略/词汇导出到文件从数据库**或**导入策略/词汇并发布到数据库文件从**，，然后单击**下一步**。  

4. 上**策略存储区**页上，从下拉列表中，选择可用的 SQL Server 计算机和数据库，然后单击**下一步**。  

5. 上**导出策略/词汇**页上，执行以下操作，并单击**下一步**。  

   1.  选择**策略**或**词汇**具体取决于你想要导出/导入。  

   2.  从**策略/词汇**下拉列表中，选择所需的策略/词汇。  

   3.  单击**浏览**选择定义文件。  

6. 查看服务器、 数据库和策略或词汇信息，然后单击**下一步**。  

7. 完成导入或导出后，单击**下一步**。  

8. 查看导入或导出的完成状态，然后单击**完成**。
