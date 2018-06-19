---
title: 不包括从 CertSrv 托管在单台计算机部署上的路径 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed paths
- certificate server (CertSrv)
- certificates, certificate server (CertSrv)
ms.assetid: 39916663-b80e-49d8-ba9b-49276eb564fc
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c77fc1733859cd903bafcebc26162323feff82d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207429"
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a><span data-ttu-id="baba4-102">从托管在单台计算机部署上的路径中排除 CertSrv</span><span class="sxs-lookup"><span data-stu-id="baba4-102">Excluding CertSrv from Managed Paths on a Single-Computer Deployment</span></span>
<span data-ttu-id="baba4-103">如果你已经部署了[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]单台计算机上，并且也安装证书服务器在同一台计算机，你需要从托管路径中排除证书服务器 (CertSrv) [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] SharePoint Server 管理中心。</span><span class="sxs-lookup"><span data-stu-id="baba4-103">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer and also installed the certificate server on the same computer, you need to exclude the certificate server (CertSrv) from the managed paths in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] SharePoint Server Central Administration.</span></span>  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a><span data-ttu-id="baba4-104">若要从托管路径排除 CertSrv</span><span class="sxs-lookup"><span data-stu-id="baba4-104">To exclude CertSrv from the managed paths</span></span>  
  
1.  <span data-ttu-id="baba4-105">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="baba4-105">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
2.  <span data-ttu-id="baba4-106">在管理中心窗口中，在**虚拟服务器配置**部分中，单击**配置虚拟服务器设置**。</span><span class="sxs-lookup"><span data-stu-id="baba4-106">In the Central Administration window, in the **Virtual Server Configuration** section, click **Configure virtual server settings**.</span></span>  
  
3.  <span data-ttu-id="baba4-107">在虚拟服务器列表窗口中，单击**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="baba4-107">In the Virtual Server List window, click **Default Web Site**.</span></span>  
  
4.  <span data-ttu-id="baba4-108">在虚拟服务器设置窗口中，在**虚拟服务器管理**部分中，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="baba4-108">In the Virtual Server Settings window, in the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
5.  <span data-ttu-id="baba4-109">在定义管理路径窗口中，在**添加新路径**部分中，输入**CertSrv**中**路径**文本框。</span><span class="sxs-lookup"><span data-stu-id="baba4-109">In the Define Managed Paths window, in the **Add a New Path** section, enter **CertSrv** in the **Path** text box.</span></span> <span data-ttu-id="baba4-110">在**类型**部分中，单击**排除路径**。</span><span class="sxs-lookup"><span data-stu-id="baba4-110">In the **Type** section, click **Excluded Path**.</span></span> <span data-ttu-id="baba4-111">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="baba4-111">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="baba4-112">关闭定义管理路径窗口。</span><span class="sxs-lookup"><span data-stu-id="baba4-112">Close the Define Managed Paths window.</span></span>