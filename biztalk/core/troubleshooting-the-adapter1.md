---
title: JD Edwards EnterpriseOne 适配器疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5a55e52-039a-4aea-8251-b697fd061ddc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d6ba3fdb8789f7d258291aee05d9e7b481e905a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306394"
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="48288-102">适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="48288-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="48288-103">本主题包含有助于您确定和解决使用用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器时可能遇到的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="48288-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a><span data-ttu-id="48288-104">不能在发送端口属性中使用通配符</span><span class="sxs-lookup"><span data-stu-id="48288-104">Cannot use wildcards in send port properties</span></span>  
 <span data-ttu-id="48288-105">用于 JD Edwards Enterprise One 适配器不支持在以下发送端口属性字段中使用通配符：</span><span class="sxs-lookup"><span data-stu-id="48288-105">Adapter for JD Edwards Enterprise One does not support using wildcards in the following send port property fields:</span></span>  
  
-   <span data-ttu-id="48288-106">用户名</span><span class="sxs-lookup"><span data-stu-id="48288-106">Username</span></span>  
  
-   <span data-ttu-id="48288-107">JDE 环境</span><span class="sxs-lookup"><span data-stu-id="48288-107">JDE Environment</span></span>  
  
-   <span data-ttu-id="48288-108">主机</span><span class="sxs-lookup"><span data-stu-id="48288-108">Host</span></span>  
  
-   <span data-ttu-id="48288-109">Port</span><span class="sxs-lookup"><span data-stu-id="48288-109">Port</span></span>  
  
-   <span data-ttu-id="48288-110">Java_Home</span><span class="sxs-lookup"><span data-stu-id="48288-110">Java_Home</span></span>  
  
-   <span data-ttu-id="48288-111">JDE JAR 文件</span><span class="sxs-lookup"><span data-stu-id="48288-111">JDE JAR Files</span></span>  
  
-   <span data-ttu-id="48288-112">安全服务器名称</span><span class="sxs-lookup"><span data-stu-id="48288-112">Security Server Name</span></span>  
  
-   <span data-ttu-id="48288-113">服务名称连接</span><span class="sxs-lookup"><span data-stu-id="48288-113">Service Name Connect</span></span>  
  
-   <span data-ttu-id="48288-114">数据源名称</span><span class="sxs-lookup"><span data-stu-id="48288-114">Data Source Name</span></span>  
  
-   <span data-ttu-id="48288-115">数据库所有者</span><span class="sxs-lookup"><span data-stu-id="48288-115">Database Owner</span></span>  
  
-   <span data-ttu-id="48288-116">数据库服务器名称</span><span class="sxs-lookup"><span data-stu-id="48288-116">Database Server Name</span></span>  
  
-   <span data-ttu-id="48288-117">数据库类型</span><span class="sxs-lookup"><span data-stu-id="48288-117">Database Type</span></span>  
  
-   <span data-ttu-id="48288-118">物理数据库名称</span><span class="sxs-lookup"><span data-stu-id="48288-118">Physical Database Name</span></span>  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="48288-119">连接到 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="48288-119">Connecting to Oracle database</span></span>  
 <span data-ttu-id="48288-120">与 JD Edwards 一起使用 Oracle 数据库时必须修改 jdeinterop.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="48288-120">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="48288-121">使用单点登录 [JDBJ-ORACLE] 部分定义 Oracle tnsnames 位置;必须使用数据库参数;和 SQLNET。ORA 文件必须存在于 BizTalk Server 计算机 （这应为包含在 Oracle 客户端） 上。</span><span class="sxs-lookup"><span data-stu-id="48288-121">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="48288-122">以下代码添加到 jdeinterop.ini 文件：</span><span class="sxs-lookup"><span data-stu-id="48288-122">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="48288-123">在 [JDBJ-ORACLE]:</span><span class="sxs-lookup"><span data-stu-id="48288-123">Under [JDBj-ORACLE]:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="48288-124">在 [JDBJ-BOOTSTRAP DATA SOURCE]:</span><span class="sxs-lookup"><span data-stu-id="48288-124">Under [JDBj-BOOTSTRAP DATA SOURCE]:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="48288-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="48288-125">See Also</span></span>  
 <span data-ttu-id="48288-126">[添加适配器，并创建项目](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md) </span><span class="sxs-lookup"><span data-stu-id="48288-126">[Add the adapter, and create the artifacts](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md) </span></span>  
 [<span data-ttu-id="48288-127">Troubleshooting JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="48288-127">Troubleshooting JD Edwards EnterpriseOne</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)