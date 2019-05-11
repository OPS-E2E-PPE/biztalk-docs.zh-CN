---
title: 支持安全套接字层 (SSL) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSL
ms.assetid: 012a5be0-bab8-4a60-9d63-b9684b91e4a7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb8d38a6d381069d6e240187f2ca956f09b774f5
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529820"
---
# <a name="supporting-secure-sockets-layer-ssl"></a><span data-ttu-id="de531-102">支持安全套接字层 (SSL)</span><span class="sxs-lookup"><span data-stu-id="de531-102">Supporting Secure Sockets Layer (SSL)</span></span>
<span data-ttu-id="de531-103">若要在部署中的客户端计算机和 MRSR 服务器之间实现安全套接字层 (SSL) 协议，你需要请求并在 Internet 信息服务 (IIS) 服务器上配置的"服务器身份验证"证书。</span><span class="sxs-lookup"><span data-stu-id="de531-103">To implement the Secure Sockets Layer (SSL) protocol in your deployment between the client computers and the MRSR servers, you need to request and configure a "Server Authentication" certificate on your Internet Information Services (IIS) servers.</span></span>  
  
 <span data-ttu-id="de531-104">应为网络负载平衡 (NLB) 群集中的所有服务器使用一个证书。</span><span class="sxs-lookup"><span data-stu-id="de531-104">One certificate should be used for all the servers in your Network Load Balancing (NLB) cluster.</span></span> <span data-ttu-id="de531-105">您应确保在证书请求中使用的名称是虚拟的主机名而不是单独的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="de531-105">You should ensure that the name used in the certificate request is the virtual host name instead of an individual server name.</span></span>