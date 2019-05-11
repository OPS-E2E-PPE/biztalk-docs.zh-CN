---
title: 导出证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting certificates
- certificates, exporting
ms.assetid: edeeb300-19d6-44a8-b730-dcd15891cdf9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00fb00a1b256be192ce591b2b11ec70ab9b9d398
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283725"
---
# <a name="exporting-certificates"></a><span data-ttu-id="c5e22-102">导出证书</span><span class="sxs-lookup"><span data-stu-id="c5e22-102">Exporting Certificates</span></span>
<span data-ttu-id="c5e22-103">本主题介绍如何使用证书导出向导导出的证书。</span><span class="sxs-lookup"><span data-stu-id="c5e22-103">This topic describes how to export a certificate by using the Certificate Export Wizard.</span></span> <span data-ttu-id="c5e22-104">使用此向导导出公共证书或私用证书。</span><span class="sxs-lookup"><span data-stu-id="c5e22-104">Use this wizard to export either a public certificate or a private certificate.</span></span>  
  
### <a name="to-export-a-partner-certificate"></a><span data-ttu-id="c5e22-105">若要导出合作伙伴证书</span><span class="sxs-lookup"><span data-stu-id="c5e22-105">To export a partner certificate</span></span>  
  
1. <span data-ttu-id="c5e22-106">单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] ，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.</span><span class="sxs-lookup"><span data-stu-id="c5e22-106">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="c5e22-107">展开**证书 （本地计算机）**，展开**其他人**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="c5e22-107">Expand **Certificates (Local Computer)**, expand **Other People**, and then click **Certificates**.</span></span>  
  
3. <span data-ttu-id="c5e22-108">在右窗格中，右键单击证书名称，指向**的所有任务**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="c5e22-108">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4. <span data-ttu-id="c5e22-109">上**欢迎使用证书导出向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c5e22-109">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="c5e22-110">上**导出文件格式**页上，选择你想要使用的文件的格式。</span><span class="sxs-lookup"><span data-stu-id="c5e22-110">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="c5e22-111">此格式通常为 DER 编码二进制 x.509，用于导出二进制编码的文件，或 Base-64 编码 x.509，用于导出的 Base-64 编码文件。</span><span class="sxs-lookup"><span data-stu-id="c5e22-111">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c5e22-112">对证书采用 Base-64 编码，可以在 UNIX 服务器上使用证书。</span><span class="sxs-lookup"><span data-stu-id="c5e22-112">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
6. <span data-ttu-id="c5e22-113">上**导出的文件**页上，单击**浏览**，找到你想要将文件存储，其中类型的文件的名称，单击**下一步**，然后单击**完成**.</span><span class="sxs-lookup"><span data-stu-id="c5e22-113">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-export-the-home-organization-certificate"></a><span data-ttu-id="c5e22-114">若要导出本组织证书</span><span class="sxs-lookup"><span data-stu-id="c5e22-114">To export the home organization certificate</span></span>  
  
1. <span data-ttu-id="c5e22-115">单击**启动**，单击**运行**，类型**runas /user:\<承载服务\>mmc**，其中\< *hostservice* \>是安装 Microsoft 时与主机服务关联的服务名称[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]，然后单击**确定**中运行 Microsoft 管理控制台 (MMC)主机服务的上下文。</span><span class="sxs-lookup"><span data-stu-id="c5e22-115">Click **Start**, click **Run**, type **runas /user:\<host service\> mmc**, where \<*hostservice*\> is the name of the service that you associated with the host service when you installed Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], and then click **OK** to run the Microsoft Management Console (MMC) in the context of the host service.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c5e22-116">在运行**runas**命令可以获得主机服务，以访问本组织证书所需的标识。</span><span class="sxs-lookup"><span data-stu-id="c5e22-116">You run the **runas** command to assume the identity of the host service, which is required to access the home-organization certificate.</span></span>  
  
2. <span data-ttu-id="c5e22-117">展开**证书-当前用户**，展开**个人**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="c5e22-117">Expand **Certificates - Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
3. <span data-ttu-id="c5e22-118">在右窗格中，右键单击证书名称，指向**的所有任务**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="c5e22-118">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4. <span data-ttu-id="c5e22-119">上**欢迎使用证书导出向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c5e22-119">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="c5e22-120">若要导出公钥与证书的私钥关联，将保留**否，不导出私钥**选定。</span><span class="sxs-lookup"><span data-stu-id="c5e22-120">To export the public key associated with the private key of a certificate, leave **No, do not export the private key** selected.</span></span> <span data-ttu-id="c5e22-121">若要导出的私钥，请选择**是，导出私钥**。</span><span class="sxs-lookup"><span data-stu-id="c5e22-121">To export the private key, select **Yes, export the private key**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c5e22-122">如果选择**是，导出私钥**，强烈建议不要向合作伙伴发送生成的文件。</span><span class="sxs-lookup"><span data-stu-id="c5e22-122">If you select **Yes, export the private key**, it is highly recommended that you do not send the resulting file to a partner.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c5e22-123">**是，导出私钥**选项将不可用，如果你未作私钥可导出时您首次导入它。</span><span class="sxs-lookup"><span data-stu-id="c5e22-123">The **Yes, export the private key** option will not be available if you did not make the private key exportable when you first imported it.</span></span>  
  
6. <span data-ttu-id="c5e22-124">上**导出文件格式**页上，选择你想要使用的文件的格式。</span><span class="sxs-lookup"><span data-stu-id="c5e22-124">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="c5e22-125">此格式通常为 DER 编码二进制 x.509，用于导出二进制编码的文件，或 Base-64 编码 x.509，用于导出的 Base-64 编码文件。</span><span class="sxs-lookup"><span data-stu-id="c5e22-125">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c5e22-126">对证书采用 Base-64 编码，可以在 UNIX 服务器上使用证书。</span><span class="sxs-lookup"><span data-stu-id="c5e22-126">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
7. <span data-ttu-id="c5e22-127">上**导出的文件**页上，单击**浏览**，找到你想要将文件存储，其中类型的文件的名称，单击**下一步**，然后单击**完成**.</span><span class="sxs-lookup"><span data-stu-id="c5e22-127">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e22-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5e22-128">See Also</span></span>  
 [<span data-ttu-id="c5e22-129">管理证书</span><span class="sxs-lookup"><span data-stu-id="c5e22-129">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)