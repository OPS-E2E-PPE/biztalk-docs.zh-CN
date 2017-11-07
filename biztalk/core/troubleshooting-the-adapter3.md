---
title: "解决博士 Edwards OneWorld 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba2dd62e1d4b6dc0af1845d3129e69dbe582226
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="c12f2-102">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="c12f2-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="c12f2-103">本主题包含的信息可以帮助您确定和解决使用 JD Edwards OneWorld 的 Microsoft BizTalk 适配器时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="c12f2-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a><span data-ttu-id="c12f2-104">不能在发送和接收端口属性中使用通配符</span><span class="sxs-lookup"><span data-stu-id="c12f2-104">Cannot use wildcards in send and receive port properties</span></span>  
 <span data-ttu-id="c12f2-105">JD Edwards One World 的适配器不支持在以下属性字段中使用通配符：</span><span class="sxs-lookup"><span data-stu-id="c12f2-105">Adapter for JD Edwards One World does not support using wildcards in the following property fields:</span></span>  
  
|<span data-ttu-id="c12f2-106">发送端口属性</span><span class="sxs-lookup"><span data-stu-id="c12f2-106">Send Port Property</span></span>|<span data-ttu-id="c12f2-107">接收端口属性</span><span class="sxs-lookup"><span data-stu-id="c12f2-107">Receive Port Property</span></span>|  
|------------------------|---------------------------|  
|<span data-ttu-id="c12f2-108">用户名</span><span class="sxs-lookup"><span data-stu-id="c12f2-108">Username</span></span>|<span data-ttu-id="c12f2-109">事件文件路径</span><span class="sxs-lookup"><span data-stu-id="c12f2-109">Event File Path</span></span>|  
|<span data-ttu-id="c12f2-110">JDE 环境</span><span class="sxs-lookup"><span data-stu-id="c12f2-110">JDE Environment</span></span>|<span data-ttu-id="c12f2-111">事件目标名称前缀</span><span class="sxs-lookup"><span data-stu-id="c12f2-111">Event Target Name prefix</span></span>|  
|<span data-ttu-id="c12f2-112">主机</span><span class="sxs-lookup"><span data-stu-id="c12f2-112">Host</span></span>||  
|<span data-ttu-id="c12f2-113">端口</span><span class="sxs-lookup"><span data-stu-id="c12f2-113">Port</span></span>||  
|<span data-ttu-id="c12f2-114">Java_Home</span><span class="sxs-lookup"><span data-stu-id="c12f2-114">Java_Home</span></span>||  
|<span data-ttu-id="c12f2-115">JDE JAR 文件</span><span class="sxs-lookup"><span data-stu-id="c12f2-115">JDE JAR Files</span></span>||  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="c12f2-116">连接到 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="c12f2-116">Connecting to Oracle database</span></span>  
 <span data-ttu-id="c12f2-117">将 Oracle 数据库与 JD Edwards 一起使用时，必须修改 jdeinterop.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="c12f2-117">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="c12f2-118">[JDBj-ORACLE] 部分使用单一登录功能定义 Oracle tnsnames 位置；必须使用数据库参数；BizTalk Server 计算机上必须存在 SQLNET.ORA 文件（此文件应包含在 Oracle 客户端）。</span><span class="sxs-lookup"><span data-stu-id="c12f2-118">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="c12f2-119">将以下内容添加到 jdeinterop.ini 文件：</span><span class="sxs-lookup"><span data-stu-id="c12f2-119">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="c12f2-120">在 [JDBj-ORACLE] 下键入：</span><span class="sxs-lookup"><span data-stu-id="c12f2-120">Under [JDBj-ORACLE], type:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="c12f2-121">在 [JDBj-BOOTSTRAP DATA SOURCE] 下键入：</span><span class="sxs-lookup"><span data-stu-id="c12f2-121">Under [JDBj-BOOTSTRAP DATA SOURCE], type:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c12f2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c12f2-122">See Also</span></span>  
 <span data-ttu-id="c12f2-123">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   </span><span class="sxs-lookup"><span data-stu-id="c12f2-123">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   </span></span>  
 [<span data-ttu-id="c12f2-124">JD Edwards OneWorld 疑难解答</span><span class="sxs-lookup"><span data-stu-id="c12f2-124">Troubleshoot JD Edwards OneWorld</span></span>](../core/troubleshooting-jd-edwards-oneworld.md)