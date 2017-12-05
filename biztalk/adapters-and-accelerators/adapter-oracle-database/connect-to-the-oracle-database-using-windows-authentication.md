---
title: "连接到 Oracle 数据库使用 Windows 身份验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73b42a1b-1105-4278-bf8a-62cf0cffb08f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 840435ce334863a4b76e6ac7da0d8dd64e7d4937
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a><span data-ttu-id="5f0e2-102">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="5f0e2-102">Connect to the Oracle Database Using Windows Authentication</span></span>
<span data-ttu-id="5f0e2-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]使适配器客户端以使用 Windows 身份验证来建立与 Oracle 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] enables adapter clients to use Windows Authentication to establish a connection with the Oracle database.</span></span> <span data-ttu-id="5f0e2-104">若要使用 Windows 身份验证，适配器客户端必须指定"/"用户名和将密码留空。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-104">To use Windows Authentication, the adapter clients must specify “/” for user name and leave the password blank.</span></span> <span data-ttu-id="5f0e2-105">有关连接到 Oracle 数据库使用 Windows 身份验证的详细信息，请参阅[连接到 Visual Studio 使用使用适配器服务中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-105">For more information about connecting to the Oracle database using Windows Authentication, see [Connect to Oracle Database in Visual Studio using the Consume Adapter Service](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).</span></span>  
  
 <span data-ttu-id="5f0e2-106">若要启用适配器客户端使用 Windows 身份验证来连接到 Oracle 数据库，必须运行 Oracle 数据库的计算机上执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-106">To enable adapter clients to use Windows Authentication to connect to an Oracle database, you must perform the following tasks on the computer running the Oracle database.</span></span>  
  
1.  <span data-ttu-id="5f0e2-107">请确保`sqlnet.ora`上客户端和服务器上，可在使用文件`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`，具有以下项：</span><span class="sxs-lookup"><span data-stu-id="5f0e2-107">Make sure that the `sqlnet.ora` file on both the client and the server, available under `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, has the following entry:</span></span>  
  
    ```  
    SQLNET.AUTHENTICATION_SERVICES= (NTS)  
    ```  
  
2.  <span data-ttu-id="5f0e2-108">以 sysdba 身份连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-108">Connect to the Oracle database as SYSDBA.</span></span>  
  
3.  <span data-ttu-id="5f0e2-109">为外部用户的 Oracle 数据库中创建的 Windows 用户。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-109">Create the Windows user as an external user in the Oracle database.</span></span> <span data-ttu-id="5f0e2-110">请注意，用户名称必须以大写形式。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-110">Note that the user name must be in upper case.</span></span>  
  
    ```  
    CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
    ```  
  
4.  <span data-ttu-id="5f0e2-111">向用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-111">Grant privileges to the user.</span></span>  
  
    ```  
    GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
    ```  
  
5.  <span data-ttu-id="5f0e2-112">若要启用新创建的用户，登录使用 Windows 身份验证，访问 Oracle 数据库项目，可以对 SCOTT 架构更改用户的架构。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-112">To enable the newly created user, logging in using Windows Authentication, to access the Oracle database artifacts, you can change the user’s schema to the SCOTT schema.</span></span> <span data-ttu-id="5f0e2-113">当用户登录时更改为 SCOTT 的用户的默认架构的登录脚本，可以添加以下 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-113">You can add the following SQL command to the logon script that changes the user’s default schema to SCOTT when the user logs on.</span></span>  
  
    ```  
    alter session set current_schema=SCOTT;  
    ```  
  
6.  <span data-ttu-id="5f0e2-114">即使你对 SCOTT 架构更改的用户架构，仍将能够浏览并生成元数据中使用时看到的 Oracle 数据库项目[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-114">Even though you changed the schema of the user to the SCOTT schema, you will still not be able to see the Oracle database artifacts while browsing and generating metadata using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="5f0e2-115">这是因为新创建的用户没有 SCOTT 架构的权限。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-115">This is because the newly created user does not have permissions for the SCOTT schema.</span></span> <span data-ttu-id="5f0e2-116">请确保您提供给新创建的用户的 SCOTT 架构的权限。</span><span class="sxs-lookup"><span data-stu-id="5f0e2-116">Make sure you provided permission for the SCOTT schema to the newly created user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f0e2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f0e2-117">See Also</span></span>  
 <span data-ttu-id="5f0e2-118">[配置 Oracle 数据库适配器 Oracle 客户端](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5f0e2-118">[Configure the Oracle Client for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md) </span></span>  
[<span data-ttu-id="5f0e2-119">创建与 Oracle 数据库的连接</span><span class="sxs-lookup"><span data-stu-id="5f0e2-119">Create a connection to the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)