---
title: JD Edwards OneWorld 适配器疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac3c1d96de7faaf4200f9ee93387cc4a9a36933
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306413"
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="8bff6-102">适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="8bff6-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="8bff6-103">本主题包含有助于您确定和解决使用用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器时可能遇到的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="8bff6-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a><span data-ttu-id="8bff6-104">不能使用通配符在发送和接收端口属性</span><span class="sxs-lookup"><span data-stu-id="8bff6-104">Cannot use wildcards in send and receive port properties</span></span>  
 <span data-ttu-id="8bff6-105">JD Edwards One World 的适配器不支持以下属性字段中使用通配符：</span><span class="sxs-lookup"><span data-stu-id="8bff6-105">Adapter for JD Edwards One World does not support using wildcards in the following property fields:</span></span>  
  
|<span data-ttu-id="8bff6-106">发送端口属性</span><span class="sxs-lookup"><span data-stu-id="8bff6-106">Send Port Property</span></span>|<span data-ttu-id="8bff6-107">接收端口属性</span><span class="sxs-lookup"><span data-stu-id="8bff6-107">Receive Port Property</span></span>|  
|------------------------|---------------------------|  
|<span data-ttu-id="8bff6-108">用户名</span><span class="sxs-lookup"><span data-stu-id="8bff6-108">Username</span></span>|<span data-ttu-id="8bff6-109">事件文件路径</span><span class="sxs-lookup"><span data-stu-id="8bff6-109">Event File Path</span></span>|  
|<span data-ttu-id="8bff6-110">JDE 环境</span><span class="sxs-lookup"><span data-stu-id="8bff6-110">JDE Environment</span></span>|<span data-ttu-id="8bff6-111">事件目标名称前缀</span><span class="sxs-lookup"><span data-stu-id="8bff6-111">Event Target Name prefix</span></span>|  
|<span data-ttu-id="8bff6-112">主机</span><span class="sxs-lookup"><span data-stu-id="8bff6-112">Host</span></span>||  
|<span data-ttu-id="8bff6-113">Port</span><span class="sxs-lookup"><span data-stu-id="8bff6-113">Port</span></span>||  
|<span data-ttu-id="8bff6-114">Java_Home</span><span class="sxs-lookup"><span data-stu-id="8bff6-114">Java_Home</span></span>||  
|<span data-ttu-id="8bff6-115">JDE JAR 文件</span><span class="sxs-lookup"><span data-stu-id="8bff6-115">JDE JAR Files</span></span>||  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="8bff6-116">连接到 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="8bff6-116">Connecting to Oracle database</span></span>  
 <span data-ttu-id="8bff6-117">与 JD Edwards 一起使用 Oracle 数据库时必须修改 jdeinterop.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="8bff6-117">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="8bff6-118">使用单点登录 [JDBJ-ORACLE] 部分定义 Oracle tnsnames 位置;必须使用数据库参数;和 SQLNET。ORA 文件必须存在于 BizTalk Server 计算机 （这应为包含在 Oracle 客户端） 上。</span><span class="sxs-lookup"><span data-stu-id="8bff6-118">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="8bff6-119">以下代码添加到 jdeinterop.ini 文件：</span><span class="sxs-lookup"><span data-stu-id="8bff6-119">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="8bff6-120">在 [JDBJ-ORACLE] 下键入：</span><span class="sxs-lookup"><span data-stu-id="8bff6-120">Under [JDBj-ORACLE], type:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="8bff6-121">在 [JDBJ-BOOTSTRAP DATA SOURCE] 下键入：</span><span class="sxs-lookup"><span data-stu-id="8bff6-121">Under [JDBj-BOOTSTRAP DATA SOURCE], type:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8bff6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bff6-122">See Also</span></span>  
 <span data-ttu-id="8bff6-123">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   </span><span class="sxs-lookup"><span data-stu-id="8bff6-123">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   </span></span>  
 [<span data-ttu-id="8bff6-124">JD Edwards OneWorld 疑难解答</span><span class="sxs-lookup"><span data-stu-id="8bff6-124">Troubleshoot JD Edwards OneWorld</span></span>](../core/troubleshooting-jd-edwards-oneworld.md)