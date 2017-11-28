---
title: "故障排除 Adapter3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards OneWorld adapters], connecting [Oracle databases]
- JD Edwards OneWorld adapters, troubleshooting
- troubleshooting [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], troubleshooting
- Oracle databases, connecting [JD Edwards OneWorld adapters]
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15197bcdc84e813d31a8d5292f5559aca1f8ae01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="47fb9-102">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="47fb9-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="47fb9-103">本主题包含的信息可以帮助您确定和解决使用 JD Edwards OneWorld 的 Microsoft BizTalk 适配器时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="47fb9-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a><span data-ttu-id="47fb9-104">不能在发送和接收端口属性中使用通配符</span><span class="sxs-lookup"><span data-stu-id="47fb9-104">Cannot use wildcards in send and receive port properties</span></span>  
 <span data-ttu-id="47fb9-105">JD Edwards One World 的适配器不支持在以下属性字段中使用通配符：</span><span class="sxs-lookup"><span data-stu-id="47fb9-105">Adapter for JD Edwards One World does not support using wildcards in the following property fields:</span></span>  
  
|<span data-ttu-id="47fb9-106">发送端口属性</span><span class="sxs-lookup"><span data-stu-id="47fb9-106">Send Port Property</span></span>|<span data-ttu-id="47fb9-107">接收端口属性</span><span class="sxs-lookup"><span data-stu-id="47fb9-107">Receive Port Property</span></span>|  
|------------------------|---------------------------|  
|<span data-ttu-id="47fb9-108">用户名</span><span class="sxs-lookup"><span data-stu-id="47fb9-108">Username</span></span>|<span data-ttu-id="47fb9-109">事件文件路径</span><span class="sxs-lookup"><span data-stu-id="47fb9-109">Event File Path</span></span>|  
|<span data-ttu-id="47fb9-110">JDE 环境</span><span class="sxs-lookup"><span data-stu-id="47fb9-110">JDE Environment</span></span>|<span data-ttu-id="47fb9-111">事件目标名称前缀</span><span class="sxs-lookup"><span data-stu-id="47fb9-111">Event Target Name prefix</span></span>|  
|<span data-ttu-id="47fb9-112">主机</span><span class="sxs-lookup"><span data-stu-id="47fb9-112">Host</span></span>||  
|<span data-ttu-id="47fb9-113">端口</span><span class="sxs-lookup"><span data-stu-id="47fb9-113">Port</span></span>||  
|<span data-ttu-id="47fb9-114">Java_Home</span><span class="sxs-lookup"><span data-stu-id="47fb9-114">Java_Home</span></span>||  
|<span data-ttu-id="47fb9-115">JDE JAR 文件</span><span class="sxs-lookup"><span data-stu-id="47fb9-115">JDE JAR Files</span></span>||  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="47fb9-116">连接到 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="47fb9-116">Connecting to Oracle database</span></span>  
 <span data-ttu-id="47fb9-117">将 Oracle 数据库与 JD Edwards 一起使用时，必须修改 jdeinterop.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="47fb9-117">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="47fb9-118">[JDBj-ORACLE] 部分使用单一登录功能定义 Oracle tnsnames 位置；必须使用数据库参数；BizTalk Server 计算机上必须存在 SQLNET.ORA 文件（此文件应包含在 Oracle 客户端）。</span><span class="sxs-lookup"><span data-stu-id="47fb9-118">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="47fb9-119">将以下内容添加到 jdeinterop.ini 文件：</span><span class="sxs-lookup"><span data-stu-id="47fb9-119">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="47fb9-120">在 [JDBj-ORACLE] 下键入：</span><span class="sxs-lookup"><span data-stu-id="47fb9-120">Under [JDBj-ORACLE], type:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="47fb9-121">在 [JDBj-BOOTSTRAP DATA SOURCE] 下键入：</span><span class="sxs-lookup"><span data-stu-id="47fb9-121">Under [JDBj-BOOTSTRAP DATA SOURCE], type:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="47fb9-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47fb9-122">See Also</span></span>  
 <span data-ttu-id="47fb9-123">[如何为博士 Edwards OneWorld 创建发送端口](../core/how-to-create-send-ports-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="47fb9-123">[How to Create Send Ports for JD Edwards OneWorld](../core/how-to-create-send-ports-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="47fb9-124">故障排除博士 Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="47fb9-124">Troubleshooting JD Edwards OneWorld</span></span>](../core/troubleshooting-jd-edwards-oneworld.md)