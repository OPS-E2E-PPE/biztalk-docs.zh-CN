---
title: "故障排除 Adapter1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, wildcard characters
- adapters [JD Edwards EnterpriseOne adapters], wildcard characters
- wildcard characters, JD Edwards EnterpriseOne adapters
ms.assetid: f5a55e52-039a-4aea-8251-b697fd061ddc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b77b42854a58d7fe8ffafd177e91f327a7f5e7e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="8b8e1-102">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="8b8e1-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="8b8e1-103">本主题包含可帮助您标识和解决使用用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器时可能遇到的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="8b8e1-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a><span data-ttu-id="8b8e1-104">无法在发送端口属性中使用通配符</span><span class="sxs-lookup"><span data-stu-id="8b8e1-104">Cannot use wildcards in send port properties</span></span>  
 <span data-ttu-id="8b8e1-105">用于 JD Edwards Enterprise One 的适配器不支持在以下发送端口属性字段中使用通配符：</span><span class="sxs-lookup"><span data-stu-id="8b8e1-105">Adapter for JD Edwards Enterprise One does not support using wildcards in the following send port property fields:</span></span>  
  
-   <span data-ttu-id="8b8e1-106">用户名</span><span class="sxs-lookup"><span data-stu-id="8b8e1-106">Username</span></span>  
  
-   <span data-ttu-id="8b8e1-107">JDE 环境</span><span class="sxs-lookup"><span data-stu-id="8b8e1-107">JDE Environment</span></span>  
  
-   <span data-ttu-id="8b8e1-108">主机</span><span class="sxs-lookup"><span data-stu-id="8b8e1-108">Host</span></span>  
  
-   <span data-ttu-id="8b8e1-109">端口</span><span class="sxs-lookup"><span data-stu-id="8b8e1-109">Port</span></span>  
  
-   <span data-ttu-id="8b8e1-110">Java_Home</span><span class="sxs-lookup"><span data-stu-id="8b8e1-110">Java_Home</span></span>  
  
-   <span data-ttu-id="8b8e1-111">JDE JAR 文件</span><span class="sxs-lookup"><span data-stu-id="8b8e1-111">JDE JAR Files</span></span>  
  
-   <span data-ttu-id="8b8e1-112">安全服务器名称</span><span class="sxs-lookup"><span data-stu-id="8b8e1-112">Security Server Name</span></span>  
  
-   <span data-ttu-id="8b8e1-113">服务名称连接</span><span class="sxs-lookup"><span data-stu-id="8b8e1-113">Service Name Connect</span></span>  
  
-   <span data-ttu-id="8b8e1-114">数据源名称</span><span class="sxs-lookup"><span data-stu-id="8b8e1-114">Data Source Name</span></span>  
  
-   <span data-ttu-id="8b8e1-115">数据库所有者</span><span class="sxs-lookup"><span data-stu-id="8b8e1-115">Database Owner</span></span>  
  
-   <span data-ttu-id="8b8e1-116">数据库服务器名称</span><span class="sxs-lookup"><span data-stu-id="8b8e1-116">Database Server Name</span></span>  
  
-   <span data-ttu-id="8b8e1-117">数据库类型</span><span class="sxs-lookup"><span data-stu-id="8b8e1-117">Database Type</span></span>  
  
-   <span data-ttu-id="8b8e1-118">物理数据库名称</span><span class="sxs-lookup"><span data-stu-id="8b8e1-118">Physical Database Name</span></span>  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="8b8e1-119">连接到 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="8b8e1-119">Connecting to Oracle database</span></span>  
 <span data-ttu-id="8b8e1-120">将 Oracle 数据库与 JD Edwards 一起使用时，必须修改 jdeinterop.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="8b8e1-120">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="8b8e1-121">[JDBj-ORACLE] 部分使用单一登录功能定义 Oracle tnsnames 位置；必须使用数据库参数；BizTalk Server 计算机上必须存在 SQLNET.ORA 文件（此文件应包含在 Oracle 客户端）。</span><span class="sxs-lookup"><span data-stu-id="8b8e1-121">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="8b8e1-122">将以下内容添加到 jdeinterop.ini 文件：</span><span class="sxs-lookup"><span data-stu-id="8b8e1-122">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="8b8e1-123">在 [JDBj-ORACLE] 下：</span><span class="sxs-lookup"><span data-stu-id="8b8e1-123">Under [JDBj-ORACLE]:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="8b8e1-124">在 [JDBj-BOOTSTRAP DATA SOURCE] 下：</span><span class="sxs-lookup"><span data-stu-id="8b8e1-124">Under [JDBj-BOOTSTRAP DATA SOURCE]:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8b8e1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b8e1-125">See Also</span></span>  
 <span data-ttu-id="8b8e1-126">[如何为博士 Edwards EnterpriseOne 创建发送端口](../core/how-to-create-send-ports-for-jd-edwards-enterpriseone.md) </span><span class="sxs-lookup"><span data-stu-id="8b8e1-126">[How to Create Send Ports for JD Edwards EnterpriseOne](../core/how-to-create-send-ports-for-jd-edwards-enterpriseone.md) </span></span>  
 [<span data-ttu-id="8b8e1-127">故障排除博士 Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="8b8e1-127">Troubleshooting JD Edwards EnterpriseOne</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)