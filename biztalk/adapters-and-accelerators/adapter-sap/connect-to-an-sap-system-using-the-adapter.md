---
title: 连接到 SAP 系统使用的适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI
- adapters, connecting to an SAP system
- connection string
ms.assetid: d506a948-5f4a-420b-a404-508824683099
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b8c470d294124826d79903fcdf6eef54303f646
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373670"
---
# <a name="connect-to-an-sap-system-using-the-adapter"></a><span data-ttu-id="1af75-102">连接到 SAP 系统使用的适配器</span><span class="sxs-lookup"><span data-stu-id="1af75-102">Connect to an SAP system using the adapter</span></span>
<span data-ttu-id="1af75-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求适配器客户端提供连接字符串，调用统一资源标识符 (URI) 来连接到 SAP 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="1af75-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requires adapter clients to provide a connection string, called the connection Uniform Resource Identifier (URI) to connect to the SAP system.</span></span> <span data-ttu-id="1af75-104">使用一个连接 URI，适配器客户端可以指定连接参数，以连接到外部系统。有关连接 URI 的详细信息，请参阅[创建连接到 SAP 系统](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="1af75-104">With a connection URI, adapter clients can specify connection parameters to connect to an external system.For more information about the connection URI, see [Create a connection to the SAP system](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span></span>  
  
 <span data-ttu-id="1af75-105">请确保符合安全指导原则建立与 SAP 系统的连接时。</span><span class="sxs-lookup"><span data-stu-id="1af75-105">Make sure you comply with the security guidelines when establishing a connection with an SAP system.</span></span> <span data-ttu-id="1af75-106">有关安全指导原则的详细信息，请参阅[保护 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="1af75-106">For more information about security guidelines, see [Secure your SAP applications](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md).</span></span>
  
## <a name="how-many-connections-can-the-adapter-open-to-the-sap-system"></a><span data-ttu-id="1af75-107">多少个连接可以适配器打开到 SAP 系统？</span><span class="sxs-lookup"><span data-stu-id="1af75-107">How Many Connections Can the Adapter Open to the SAP System?</span></span>  
 <span data-ttu-id="1af75-108">默认情况下，SAP 系统启用客户端打开 100 个连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="1af75-108">By default, the SAP system enables clients to open 100 connections to the SAP system.</span></span> <span data-ttu-id="1af75-109">但是，您可以运行 SAP 系统以提高对连接数的限制的计算机上设置环境变量。</span><span class="sxs-lookup"><span data-stu-id="1af75-109">However, you can set an environment variable on the computer running the SAP system to increase the limit on the number of connections.</span></span> <span data-ttu-id="1af75-110">有关详细信息，请参阅[SAP 适配器的故障排除操作问题](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1af75-110">For more information, see [Troubleshoot Operational Issues with the SAP adapter](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af75-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1af75-111">See Also</span></span>  
 [<span data-ttu-id="1af75-112">用于 mySAP Business Suite 的 BizTalk 适配器的体系结构概述</span><span class="sxs-lookup"><span data-stu-id="1af75-112">Architecture overview of the BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)