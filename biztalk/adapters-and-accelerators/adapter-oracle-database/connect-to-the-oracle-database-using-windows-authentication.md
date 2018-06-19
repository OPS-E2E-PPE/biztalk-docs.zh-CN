---
title: 连接到 Oracle 数据库使用 Windows 身份验证 |Microsoft 文档
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
ms.openlocfilehash: 840435ce334863a4b76e6ac7da0d8dd64e7d4937
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961939"
---
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a>连接到 Oracle 数据库使用 Windows 身份验证
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]使适配器客户端以使用 Windows 身份验证来建立与 Oracle 数据库的连接。 若要使用 Windows 身份验证，适配器客户端必须指定"/"用户名和将密码留空。 有关连接到 Oracle 数据库使用 Windows 身份验证的详细信息，请参阅[连接到 Visual Studio 使用使用适配器服务中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)。  
  
 若要启用适配器客户端使用 Windows 身份验证来连接到 Oracle 数据库，必须运行 Oracle 数据库的计算机上执行以下任务。  
  
1.  请确保`sqlnet.ora`上客户端和服务器上，可在使用文件`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`，具有以下项：  
  
    ```  
    SQLNET.AUTHENTICATION_SERVICES= (NTS)  
    ```  
  
2.  以 sysdba 身份连接到 Oracle 数据库。  
  
3.  为外部用户的 Oracle 数据库中创建的 Windows 用户。 请注意，用户名称必须以大写形式。  
  
    ```  
    CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
    ```  
  
4.  向用户授予权限。  
  
    ```  
    GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
    ```  
  
5.  若要启用新创建的用户，登录使用 Windows 身份验证，访问 Oracle 数据库项目，可以对 SCOTT 架构更改用户的架构。 当用户登录时更改为 SCOTT 的用户的默认架构的登录脚本，可以添加以下 SQL 命令。  
  
    ```  
    alter session set current_schema=SCOTT;  
    ```  
  
6.  即使你对 SCOTT 架构更改的用户架构，仍将能够浏览并生成元数据中使用时看到的 Oracle 数据库项目[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 这是因为新创建的用户没有 SCOTT 架构的权限。 请确保您提供给新创建的用户的 SCOTT 架构的权限。  
  
## <a name="see-also"></a>另请参阅  
 [配置 Oracle 数据库适配器 Oracle 客户端](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)   
[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)