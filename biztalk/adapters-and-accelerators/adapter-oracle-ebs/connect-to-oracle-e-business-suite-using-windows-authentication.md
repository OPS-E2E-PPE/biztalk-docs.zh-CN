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
# <a name="connect-to-oracle-e-business-suite-using-windows-authentication"></a><span data-ttu-id="0299d-102">连接到 Oracle E-business Suite 使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="0299d-102">Connect to Oracle E-Business Suite using Windows Authentication</span></span>
<span data-ttu-id="0299d-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端能够使用 Windows 身份验证建立与 Oracle E-business Suite 的连接。</span><span class="sxs-lookup"><span data-stu-id="0299d-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to use Windows Authentication to establish a connection with the Oracle E-Business Suite.</span></span> <span data-ttu-id="0299d-104">若要使用 Windows 身份验证适配器客户端必须指定"/"作为用户名，并将密码留空。</span><span class="sxs-lookup"><span data-stu-id="0299d-104">To use Windows Authentication adapter clients must specify a “/” for user name and leave the password blank.</span></span> <span data-ttu-id="0299d-105">有关连接到 Oracle E-business Suite 使用 Windows 身份验证的详细信息，请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="0299d-105">For more information about connecting to the Oracle E-Business Suite using Windows Authentication, see [Connect to the Oracle E-Business Suite in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).</span></span>  

## <a name="what-you-need-to-know"></a><span data-ttu-id="0299d-106">您需要了解</span><span class="sxs-lookup"><span data-stu-id="0299d-106">What you need to know</span></span>  
 <span data-ttu-id="0299d-107">若要使用 Windows 身份验证，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0299d-107">To use Windows Authentication, you must do the following:</span></span>  
  
-   <span data-ttu-id="0299d-108">如果**ClientCredentialType**属性设置为**数据库**、 指定"/"对于用户名，保留密码为空白以连接到 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="0299d-108">If the **ClientCredentialType** property is set to **Database**, specify “/” for the user name and leave the password blank to connect to the Oracle E-Business Suite.</span></span>  
  
-   <span data-ttu-id="0299d-109">如果**ClientCredentialType**属性设置为**EBusiness**，指定用于连接 Oracle E-business Suite 凭据。</span><span class="sxs-lookup"><span data-stu-id="0299d-109">If the **ClientCredentialType** property is set to **EBusiness**, specify the Oracle E-Business Suite credentials to connect.</span></span> <span data-ttu-id="0299d-110">此外，还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。</span><span class="sxs-lookup"><span data-stu-id="0299d-110">Also, you must specify “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>  

## <a name="enable-windows-authentication"></a><span data-ttu-id="0299d-111">启用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="0299d-111">Enable Windows Authentication</span></span>  
 <span data-ttu-id="0299d-112">若要允许使用 Windows 身份验证连接到 Oracle 数据库适配器客户端，必须运行 Oracle 数据库的计算机上执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="0299d-112">To enable adapter clients to use Windows Authentication to connect to an Oracle database, you must perform the following tasks on the computer running the Oracle database.</span></span>  
  
1. <span data-ttu-id="0299d-113">请确保`sqlnet.ora`文件在客户端和服务器，可在使用`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`，具有以下项：</span><span class="sxs-lookup"><span data-stu-id="0299d-113">Make sure that the `sqlnet.ora` file on both the client and the server, available under `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, has the following entry:</span></span>  
  
   ```  
   SQLNET.AUTHENTICATION_SERVICES= (NTS)  
   ```  
  
2. <span data-ttu-id="0299d-114">以 sysdba 身份连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="0299d-114">Connect to the Oracle database as SYSDBA.</span></span>  
  
3. <span data-ttu-id="0299d-115">Windows 用户创建为 Oracle 数据库中的外部用户。</span><span class="sxs-lookup"><span data-stu-id="0299d-115">Create the Windows user as an external user in Oracle database.</span></span> <span data-ttu-id="0299d-116">请注意，用户名称必须以大写形式。</span><span class="sxs-lookup"><span data-stu-id="0299d-116">Note that the user name must be in upper case.</span></span>  
  
   ```  
   CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
   ```  
  
4. <span data-ttu-id="0299d-117">向用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="0299d-117">Grant privileges to the user.</span></span>  
  
   ```  
   GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
   ```  
  
5. <span data-ttu-id="0299d-118">Oracle E-business Suite 项目是在应用架构下可用。</span><span class="sxs-lookup"><span data-stu-id="0299d-118">The Oracle E-Business Suite artifacts are available under the APPS schema.</span></span> <span data-ttu-id="0299d-119">若要启用新创建的用户，在使用 Windows 身份验证，以访问 Oracle E-business Suite 项目中，登录用户的架构必须更改为应用程序架构。</span><span class="sxs-lookup"><span data-stu-id="0299d-119">To enable the newly created user, logging in using Windows Authentication, to access the Oracle E-Business Suite artifacts, the user’s schema must be changed to the APPS schema.</span></span> <span data-ttu-id="0299d-120">当在用户登录时更改用户的默认架构为应用程序的登录脚本，可以添加以下 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="0299d-120">You can add the following SQL command to the logon script that changes the user’s default schema to APPS when the user logs on.</span></span>  
  
   ```  
   alter session set current_schema=APPS;  
   ```  
  
6. <span data-ttu-id="0299d-121">即使应用架构更改的用户的架构，您将仍不能在浏览和生成元数据中使用的同时查看 Oracle E-business Suite 项目[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0299d-121">Even though you changed the schema of the user to APPS schema, you will still not be able to see Oracle E-Business Suite artifacts while browsing and generating metadata using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="0299d-122">这是因为新创建的用户不具有权限的应用架构。</span><span class="sxs-lookup"><span data-stu-id="0299d-122">This is because the newly created user does not have permissions for the APPS schema.</span></span> <span data-ttu-id="0299d-123">请确保新创建的用户提供针对应用程序架构的权限。</span><span class="sxs-lookup"><span data-stu-id="0299d-123">Make sure you provided permission for the APPS schema for the newly created user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0299d-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="0299d-124">See Also</span></span>  
<span data-ttu-id="0299d-125">[配置 Oracle 客户端 E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0299d-125">[Configure the Oracle client for the E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md) </span></span>  
[<span data-ttu-id="0299d-126">创建 Oracle E-business Suite 连接 URI</span><span class="sxs-lookup"><span data-stu-id="0299d-126">Create the Oracle E-Business Suite connection URI</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)  
 [<span data-ttu-id="0299d-127">创建与 Oracle E-business Suite 的连接</span><span class="sxs-lookup"><span data-stu-id="0299d-127">Create a connection to Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)