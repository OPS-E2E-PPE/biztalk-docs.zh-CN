---
title: 导出证书 |Microsoft 文档
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
ms.openlocfilehash: 32dc7b0f73955c080f875eada2705300800df452
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964515"
---
# <a name="exporting-certificates"></a><span data-ttu-id="2bdcd-102">导出证书</span><span class="sxs-lookup"><span data-stu-id="2bdcd-102">Exporting Certificates</span></span>
<span data-ttu-id="2bdcd-103">本主题说明如何使用证书导出向导导出证书。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-103">This topic describes how to export a certificate by using the Certificate Export Wizard.</span></span> <span data-ttu-id="2bdcd-104">使用此向导可导出公用证书或私用证书。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-104">Use this wizard to export either a public certificate or a private certificate.</span></span>  
  
### <a name="to-export-a-partner-certificate"></a><span data-ttu-id="2bdcd-105">导出合作伙伴证书</span><span class="sxs-lookup"><span data-stu-id="2bdcd-105">To export a partner certificate</span></span>  
  
1.  <span data-ttu-id="2bdcd-106">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] ，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.</span><span class="sxs-lookup"><span data-stu-id="2bdcd-106">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="2bdcd-107">展开**证书 （本地计算机）**，展开**其他人**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-107">Expand **Certificates (Local Computer)**, expand **Other People**, and then click **Certificates**.</span></span>  
  
3.  <span data-ttu-id="2bdcd-108">在右窗格中，右键单击证书的名称，指向**所有任务**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-108">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4.  <span data-ttu-id="2bdcd-109">上**欢迎使用证书导出向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-109">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="2bdcd-110">上**导出文件格式**页上，选择你想要为文件使用的格式。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-110">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="2bdcd-111">此格式通常为 DER 编码二进制 x.509，用于导出二进制编码文件，或者是 Base64 编码的 x.509，用于导出 Base64 编码文件。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-111">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bdcd-112">使用 Base64 对证书编码使得可以在 UNIX 服务器上使用证书。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-112">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
6.  <span data-ttu-id="2bdcd-113">上**导出的文件**页上，单击**浏览**，找到你想要将文件存储，其中类型文件的名称，请单击**下一步**，然后单击**完成**.</span><span class="sxs-lookup"><span data-stu-id="2bdcd-113">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-export-the-home-organization-certificate"></a><span data-ttu-id="2bdcd-114">导出本组织证书</span><span class="sxs-lookup"><span data-stu-id="2bdcd-114">To export the home organization certificate</span></span>  
  
1.  <span data-ttu-id="2bdcd-115">单击**启动**，单击**运行**，类型**runas /user:\<承载服务\>mmc**，其中\< *hostservice* \>是你在安装时，在与主机服务关联的服务名称[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]，然后单击**确定**运行[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理控制台 (MMC) 的主机服务的上下文中。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-115">Click **Start**, click **Run**, type **runas /user:\<host service\> mmc**, where \<*hostservice*\> is the name of the service that you associated with the host service when you installed [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], and then click **OK** to run the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC) in the context of the host service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bdcd-116">你运行**runas**命令假定访问主页组织证书所需的主机服务的标识。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-116">You run the **runas** command to assume the identity of the host service, which is required to access the home-organization certificate.</span></span>  
  
2.  <span data-ttu-id="2bdcd-117">展开**证书-当前用户**，展开**个人**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-117">Expand **Certificates - Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
3.  <span data-ttu-id="2bdcd-118">在右窗格中，右键单击证书的名称，指向**所有任务**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-118">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4.  <span data-ttu-id="2bdcd-119">上**欢迎使用证书导出向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-119">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="2bdcd-120">若要导出的公钥与证书的私钥关联，将保留**否，不导出私钥**选。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-120">To export the public key associated with the private key of a certificate, leave **No, do not export the private key** selected.</span></span> <span data-ttu-id="2bdcd-121">若要导出的私钥，请选择**是，导出私钥**。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-121">To export the private key, select **Yes, export the private key**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bdcd-122">如果你选择**是，导出私钥**，强烈建议不要不将生成的文件发送到合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-122">If you select **Yes, export the private key**, it is highly recommended that you do not send the resulting file to a partner.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bdcd-123">**是，导出私钥**选项将不可用，如果你未做私钥可导出时你首次导入它。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-123">The **Yes, export the private key** option will not be available if you did not make the private key exportable when you first imported it.</span></span>  
  
6.  <span data-ttu-id="2bdcd-124">上**导出文件格式**页上，选择你想要为文件使用的格式。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-124">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="2bdcd-125">此格式通常为 DER 编码二进制 x.509，用于导出二进制编码文件，或者是 Base64 编码的 x.509，用于导出 Base64 编码文件。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-125">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bdcd-126">使用 Base64 对证书编码使得可以在 UNIX 服务器上使用证书。</span><span class="sxs-lookup"><span data-stu-id="2bdcd-126">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
7.  <span data-ttu-id="2bdcd-127">上**导出的文件**页上，单击**浏览**，找到你想要将文件存储，其中类型文件的名称，请单击**下一步**，然后单击**完成**.</span><span class="sxs-lookup"><span data-stu-id="2bdcd-127">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bdcd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bdcd-128">See Also</span></span>  
 [<span data-ttu-id="2bdcd-129">管理证书</span><span class="sxs-lookup"><span data-stu-id="2bdcd-129">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)