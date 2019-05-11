---
title: 连接到 Oracle 数据库使用 Windows 身份验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73b42a1b-1105-4278-bf8a-62cf0cffb08f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fae3fe99fe3d9f3d0553a7f597d02553ca034688
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529448"
---
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a>连接到 Oracle 数据库使用 Windows 身份验证
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]使适配器客户端能够使用 Windows 身份验证建立与 Oracle 数据库的连接。 若要使用 Windows 身份验证，适配器客户端必须指定"/"作为用户名并将密码留空。 有关连接到 Oracle 数据库使用 Windows 身份验证的详细信息，请参阅[连接到 Oracle 数据库，在 Visual Studio 中使用使用适配器服务](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)。  
  
 若要允许使用 Windows 身份验证连接到 Oracle 数据库适配器客户端，必须运行 Oracle 数据库的计算机上执行以下任务。  
  
1. 请确保`sqlnet.ora`文件在客户端和服务器，可在使用`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`，具有以下项：  
  
   ```  
   SQLNET.AUTHENTICATION_SERVICES= (NTS)  
   ```  
  
2. 以 sysdba 身份连接到 Oracle 数据库。  
  
3. Windows 用户创建为 Oracle 数据库中的外部用户。 请注意，用户名称必须以大写形式。  
  
   ```  
   CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
   ```  
  
4. 向用户授予权限。  
  
   ```  
   GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
   ```  
  
5. 若要启用新创建的用户记录中使用 Windows 身份验证，以访问 Oracle 数据库项目，可以到 SCOTT 架构更改用户的架构。 当用户登录时更改用户的默认架构为 SCOTT 的登录脚本，可以添加以下 SQL 命令。  
  
   ```  
   alter session set current_schema=SCOTT;  
   ```  
  
6. 即使 SCOTT 架构更改的用户的架构，您将仍不能看到继续浏览和生成元数据中使用 Oracle 数据库项目[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 这是因为新创建的用户不具有对 SCOTT 架构权限。 请确保为新创建的用户提供针对 SCOTT 架构的权限。  
  
## <a name="see-also"></a>请参阅  
 [配置 Oracle 数据库适配器的 Oracle 客户端](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)   
[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)