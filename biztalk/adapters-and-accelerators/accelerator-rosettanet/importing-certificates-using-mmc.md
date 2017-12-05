---
title: "导入使用 MMC 证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- certificates, importing
ms.assetid: 58fb1711-e295-4aa6-902e-e28e4a2cd921
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 466917e0656dfa39467a00dfa91285b3cb7cf1a1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="importing-certificates-using-mmc"></a><span data-ttu-id="164b1-102">导入证书使用 MMC</span><span class="sxs-lookup"><span data-stu-id="164b1-102">Importing Certificates Using MMC</span></span>
<span data-ttu-id="164b1-103">本主题描述如何导入数字证书[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]用于进行身份验证贸易合作伙伴，解密传入消息时，或者加密或传出消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="164b1-103">This topic describes how to import a digital certificate that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses to authenticate a trading partner, decrypt an incoming message, or encrypt or sign an outgoing message.</span></span>  
  
 <span data-ttu-id="164b1-104">此过程使用的证书管理单元接[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="164b1-104">This procedure uses the Certificates snap-in for the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="164b1-105">此手动流程将证书导入证书存储区，并要求您单独配置证书的使用。</span><span class="sxs-lookup"><span data-stu-id="164b1-105">This manual process imports a certificate into the certificate store, requiring you to configure certificate use separately.</span></span> <span data-ttu-id="164b1-106">您还可以使用 CertWizard 实用工具（该工具自动为您配置证书的使用）导入证书。</span><span class="sxs-lookup"><span data-stu-id="164b1-106">You can also import a certificate by using the CertWizard utility that automatically configures certificate use for you.</span></span>  
  
 <span data-ttu-id="164b1-107">要导入私用证书，必须使用运行 BizTalk 主机的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="164b1-107">To import private certificates, you must use the user accounts under which the BizTalk Hosts run.</span></span>  
  
### <a name="to-import-a-public-key-certificate"></a><span data-ttu-id="164b1-108">导入公钥证书</span><span class="sxs-lookup"><span data-stu-id="164b1-108">To import a public-key certificate</span></span>  
  
1.  <span data-ttu-id="164b1-109">将公钥 (.cer) 证书文件复制到服务器硬盘上的某个位置，该位置也是您正在向其复制证书的位置。</span><span class="sxs-lookup"><span data-stu-id="164b1-109">Copy the public-key (.cer) certificate file to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2.  <span data-ttu-id="164b1-110">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.</span><span class="sxs-lookup"><span data-stu-id="164b1-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
3.  <span data-ttu-id="164b1-111">在[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开**证书 （本地计算机）**。</span><span class="sxs-lookup"><span data-stu-id="164b1-111">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="164b1-112">登录用户必须对该计算机具有管理权限。</span><span class="sxs-lookup"><span data-stu-id="164b1-112">The logged-in user must have administrative permissions to the computer.</span></span>  
  
4.  <span data-ttu-id="164b1-113">右键单击**其他人**，指向**所有任务**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="164b1-113">Right-click **Other People**, point to **All Tasks**, and then click **Import**.</span></span>  
  
5.  <span data-ttu-id="164b1-114">上**证书导入向导欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="164b1-114">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="164b1-115">上**导入的文件**页上，单击**浏览**并找到包含证书文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="164b1-115">On the **File to Import** page, click **Browse** and locate the folder that contains the certificate files.</span></span> <span data-ttu-id="164b1-116">选择你想要导入证书，然后单击的文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="164b1-116">Select the file from which you want to import the certificate, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="164b1-117">上**证书存储区**页上，选择**自动选择基于证书的类型的证书**或**将所有证书都放入下列存储**.</span><span class="sxs-lookup"><span data-stu-id="164b1-117">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="164b1-118">如果你选择**将所有证书都放入下列存储**，单击**浏览**，选择证书存储中，单击**确定**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="164b1-118">If you select **Place all certificates in the following store**, click **Browse**, select the certificate store, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="164b1-119">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="164b1-119">Click **Finish**.</span></span>  
  
### <a name="to-import-a-private-key-certificate"></a><span data-ttu-id="164b1-120">导入私钥证书</span><span class="sxs-lookup"><span data-stu-id="164b1-120">To import a private-key certificate</span></span>  
  
1.  <span data-ttu-id="164b1-121">将私钥 (.pfx) 证书文件复制到服务器硬盘上的某个位置，该位置也是您正在向其复制证书的位置。</span><span class="sxs-lookup"><span data-stu-id="164b1-121">Copy private-key (.pfx) certificate files to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2.  <span data-ttu-id="164b1-122">单击**启动**，单击**运行**，类型**runas /user:\<承载服务\>mmc**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="164b1-122">Click **Start**, click **Run**, type **run as /user:\<host service\> mmc**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="164b1-123">有关\<*承载服务*\>，键入你在安装时自动为主机服务中选择服务的名称[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="164b1-123">For \<*host service*\>, type the name of the service that was automatically selected for the host service when you installed [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span>  
  
3.  <span data-ttu-id="164b1-124">键入的密码\<*承载服务*\>，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="164b1-124">Type the password for \<*host service*\>, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="164b1-125">在[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理控制台中，在**文件**菜单上，单击**添加/删除管理单元中**。</span><span class="sxs-lookup"><span data-stu-id="164b1-125">In [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
5.  <span data-ttu-id="164b1-126">在添加/删除管理单元中对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="164b1-126">In the Add/Remove Snap-in dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="164b1-127">在添加独立管理单元对话框中，选择**证书**，单击**添加**，单击**关闭**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="164b1-127">In the Add Standalone Snap-in dialog box, select **Certificates**, click **Add**, click **Close**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="164b1-128">在[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理控制台中，展开**证书-当前用户**，右键单击**个人**，指向**所有任务**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="164b1-128">In [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console, expand **Certificates - Current User**, right-click **Personal**, point to **All Tasks**, and then click **Import**.</span></span>  
  
8.  <span data-ttu-id="164b1-129">上**证书导入向导欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="164b1-129">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="164b1-130">上**导入的文件**页上，单击**浏览**并找到包含包含你想要导入的证书的.pfx 证书文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="164b1-130">On the **File to Import** page, click **Browse** and locate the folder that contains the .pfx certificate file that contains the certificate that you want to import.</span></span> <span data-ttu-id="164b1-131">选择适当的文件，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="164b1-131">Select the appropriate file, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="164b1-132">上**密码**页上，在**密码**框中，键入私钥文件的密码。</span><span class="sxs-lookup"><span data-stu-id="164b1-132">On the **Password** page, in the **Password** box, type the password for the private-key file.</span></span>  
  
11. <span data-ttu-id="164b1-133">选择**启用强私钥保护**或**标志此密钥为可导出**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="164b1-133">Select **Enable strong private key protection** or **Mark this key as exportable**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="164b1-134">上**证书存储区**页上，选择**自动选择基于证书的类型的证书**或**将所有证书都放入下列存储**.</span><span class="sxs-lookup"><span data-stu-id="164b1-134">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="164b1-135">如果你选择**将所有证书都放入下列存储**，单击**浏览**，选择存储区中，单击**确定**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="164b1-135">If you select **Place all certificates in the following store**, click **Browse**, select the store, click **OK**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="164b1-136">上**完成证书导入向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="164b1-136">On the **Completing the Certificate Import Wizard** page, click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="164b1-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="164b1-137">See Also</span></span>  
 <span data-ttu-id="164b1-138">[配置使用 MMC 导入的证书](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span><span class="sxs-lookup"><span data-stu-id="164b1-138">[Configuring Certificates Imported Using MMC](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span></span>  
 [<span data-ttu-id="164b1-139">CertWizard</span><span class="sxs-lookup"><span data-stu-id="164b1-139">CertWizard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)