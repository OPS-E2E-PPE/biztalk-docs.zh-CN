---
title: 将连接到使用 Windows 身份验证的 Oracle E-business Suite |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0937dfd9-4a94-4d65-a42c-3c5019eefde2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed71a893ef029e6524b7e71f68626c32f207f91e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961579"
---
# <a name="connect-to-oracle-e-business-suite-using-windows-authentication"></a>将连接到 Oracle E-business Suite 使用 Windows 身份验证
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端以使用 Windows 身份验证来建立与 Oracle E-business Suite 的连接。 若要使用 Windows 身份验证适配器客户端必须指定"/"用户名称并将密码保留为空。 有关将连接到 Oracle E-business Suite 使用 Windows 身份验证的详细信息，请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  

## <a name="what-you-need-to-know"></a>你需要知道  
 若要使用 Windows 身份验证，必须执行以下操作：  
  
-   如果**ClientCredentialType**属性设置为**数据库**、 指定"/"针对用户名称和将密码留空以连接到 Oracle E-business Suite。  
  
-   如果**ClientCredentialType**属性设置为**EBusiness**，指定要连接的 Oracle E-business Suite 凭据。 此外，还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。  

## <a name="enable-windows-authentication"></a>启用 Windows 身份验证  
 若要启用适配器客户端使用 Windows 身份验证来连接到 Oracle 数据库，必须运行 Oracle 数据库的计算机上执行以下任务。  
  
1.  请确保`sqlnet.ora`上客户端和服务器上，可在使用文件`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`，具有以下项：  
  
    ```  
    SQLNET.AUTHENTICATION_SERVICES= (NTS)  
    ```  
  
2.  以 sysdba 身份连接到 Oracle 数据库。  
  
3.  为外部用户 Oracle 数据库中创建的 Windows 用户。 请注意，用户名称必须以大写形式。  
  
    ```  
    CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
    ```  
  
4.  向用户授予权限。  
  
    ```  
    GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
    ```  
  
5.  Oracle E-business Suite 项目位于应用程序架构。 若要启用新创建的用户，登录使用 Windows 身份验证，访问 Oracle E-business Suite 项目中，必须将用户的架构更改为应用程序架构。 当用户登录时更改为应用程序的用户的默认架构的登录脚本，可以添加以下 SQL 命令。  
  
    ```  
    alter session set current_schema=APPS;  
    ```  
  
6.  即使你对应用架构更改的用户架构，仍将能够浏览并生成元数据中使用时查看 Oracle E-business Suite 项目[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 这是因为新创建的用户没有应用架构的权限。 请确保您为新创建的用户提供应用架构的权限。  
  
## <a name="see-also"></a>另请参阅  
[配置 Oracle 客户端为 E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)   
[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)  
 [创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)