---
title: 连接到 Oracle E-business Suite 使用 Windows 身份验证 |Microsoft Docs
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
ms.openlocfilehash: 10a9c111269e676b197c3b43e577c5e8dc6b6e97
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375628"
---
# <a name="connect-to-oracle-e-business-suite-using-windows-authentication"></a>连接到 Oracle E-business Suite 使用 Windows 身份验证
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端能够使用 Windows 身份验证建立与 Oracle E-business Suite 的连接。 若要使用 Windows 身份验证适配器客户端必须指定"/"作为用户名，并将密码留空。 有关连接到 Oracle E-business Suite 使用 Windows 身份验证的详细信息，请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  

## <a name="what-you-need-to-know"></a>您需要了解  
 若要使用 Windows 身份验证，必须执行以下操作：  
  
-   如果**ClientCredentialType**属性设置为**数据库**、 指定"/"对于用户名，保留密码为空白以连接到 Oracle E-business Suite。  
  
-   如果**ClientCredentialType**属性设置为**EBusiness**，指定用于连接 Oracle E-business Suite 凭据。 此外，还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。  

## <a name="enable-windows-authentication"></a>启用 Windows 身份验证  
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
  
5. Oracle E-business Suite 项目是在应用架构下可用。 若要启用新创建的用户，在使用 Windows 身份验证，以访问 Oracle E-business Suite 项目中，登录用户的架构必须更改为应用程序架构。 当在用户登录时更改用户的默认架构为应用程序的登录脚本，可以添加以下 SQL 命令。  
  
   ```  
   alter session set current_schema=APPS;  
   ```  
  
6. 即使应用架构更改的用户的架构，您将仍不能在浏览和生成元数据中使用的同时查看 Oracle E-business Suite 项目[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 这是因为新创建的用户不具有权限的应用架构。 请确保新创建的用户提供针对应用程序架构的权限。  
  
## <a name="see-also"></a>请参阅  
[配置 Oracle 客户端 E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)   
[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)  
 [创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)