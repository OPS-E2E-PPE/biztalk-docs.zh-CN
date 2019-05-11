---
title: 使用 MMC 导入证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- certificates, importing
ms.assetid: 58fb1711-e295-4aa6-902e-e28e4a2cd921
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d813adad739f7843308bcd3c53aa242ff97520c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283597"
---
# <a name="importing-certificates-using-mmc"></a><span data-ttu-id="b9604-102">使用 MMC 导入证书</span><span class="sxs-lookup"><span data-stu-id="b9604-102">Importing Certificates Using MMC</span></span>
<span data-ttu-id="b9604-103">本主题介绍如何导入的数字证书，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]用于验证贸易合作伙伴、 解密传入消息，或加密或签名传出消息。</span><span class="sxs-lookup"><span data-stu-id="b9604-103">This topic describes how to import a digital certificate that Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses to authenticate a trading partner, decrypt an incoming message, or encrypt or sign an outgoing message.</span></span>  
  
 <span data-ttu-id="b9604-104">此过程使用证书管理单元中的 Microsoft 管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="b9604-104">This procedure uses the Certificates snap-in for the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="b9604-105">这一手动流程将证书导入证书存储中，无需单独配置证书的使用。</span><span class="sxs-lookup"><span data-stu-id="b9604-105">This manual process imports a certificate into the certificate store, requiring you to configure certificate use separately.</span></span> <span data-ttu-id="b9604-106">此外可以通过使用自动配置为证书使用 CertWizard 实用工具导入证书。</span><span class="sxs-lookup"><span data-stu-id="b9604-106">You can also import a certificate by using the CertWizard utility that automatically configures certificate use for you.</span></span>  
  
 <span data-ttu-id="b9604-107">若要导入私用证书，必须使用 BizTalk 主机在其下运行的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b9604-107">To import private certificates, you must use the user accounts under which the BizTalk Hosts run.</span></span>  
  
### <a name="to-import-a-public-key-certificate"></a><span data-ttu-id="b9604-108">若要导入公钥证书</span><span class="sxs-lookup"><span data-stu-id="b9604-108">To import a public-key certificate</span></span>  
  
1. <span data-ttu-id="b9604-109">复制到硬盘上的位置服务器正在向其复制证书的公钥 (.cer) 证书文件。</span><span class="sxs-lookup"><span data-stu-id="b9604-109">Copy the public-key (.cer) certificate file to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2. <span data-ttu-id="b9604-110">单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.</span><span class="sxs-lookup"><span data-stu-id="b9604-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
3. <span data-ttu-id="b9604-111">在中[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开**证书 （本地计算机）**。</span><span class="sxs-lookup"><span data-stu-id="b9604-111">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="b9604-112">登录的用户必须具有计算机的管理权限。</span><span class="sxs-lookup"><span data-stu-id="b9604-112">The logged-in user must have administrative permissions to the computer.</span></span>  
  
4. <span data-ttu-id="b9604-113">右键单击**其他人**，依次指向**的所有任务**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="b9604-113">Right-click **Other People**, point to **All Tasks**, and then click **Import**.</span></span>  
  
5. <span data-ttu-id="b9604-114">上**证书导入向导欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b9604-114">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
6. <span data-ttu-id="b9604-115">上**导入的文件**页上，单击**浏览**并找到包含证书文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b9604-115">On the **File to Import** page, click **Browse** and locate the folder that contains the certificate files.</span></span> <span data-ttu-id="b9604-116">选择想要导入证书，然后单击的文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="b9604-116">Select the file from which you want to import the certificate, and then click **Open**.</span></span>  
  
7. <span data-ttu-id="b9604-117">上**证书存储区**页上，选择**自动选择基于证书的类型的证书**或**将所有证书都放入下列存储**.</span><span class="sxs-lookup"><span data-stu-id="b9604-117">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="b9604-118">如果选择**将所有证书都放入下列存储**，单击**浏览**，选择证书存储区，单击**确定**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="b9604-118">If you select **Place all certificates in the following store**, click **Browse**, select the certificate store, click **OK**, and then click **Next**.</span></span>  
  
8. <span data-ttu-id="b9604-119">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="b9604-119">Click **Finish**.</span></span>  
  
### <a name="to-import-a-private-key-certificate"></a><span data-ttu-id="b9604-120">若要导入私钥证书</span><span class="sxs-lookup"><span data-stu-id="b9604-120">To import a private-key certificate</span></span>  
  
1. <span data-ttu-id="b9604-121">复制私钥 (.pfx) 证书文件复制到硬盘上的服务器正在向其复制证书的位置。</span><span class="sxs-lookup"><span data-stu-id="b9604-121">Copy private-key (.pfx) certificate files to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2. <span data-ttu-id="b9604-122">单击**启动**，单击**运行**，类型**runas /user:\<承载服务\>mmc**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b9604-122">Click **Start**, click **Run**, type **run as /user:\<host service\> mmc**, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b9604-123">有关\<*承载服务*\>，键入你在安装时自动为主机服务中选择的服务名称[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b9604-123">For \<*host service*\>, type the name of the service that was automatically selected for the host service when you installed [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span>  
  
3. <span data-ttu-id="b9604-124">键入的密码\<*承载服务*\>，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="b9604-124">Type the password for \<*host service*\>, and then press **Enter**.</span></span>  
  
4. <span data-ttu-id="b9604-125">在 Microsoft 管理控制台中，在**文件**菜单上，单击**添加/删除管理单元中**。</span><span class="sxs-lookup"><span data-stu-id="b9604-125">In Microsoft Management Console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
5. <span data-ttu-id="b9604-126">在添加/删除管理单元对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b9604-126">In the Add/Remove Snap-in dialog box, click **Add**.</span></span>  
  
6. <span data-ttu-id="b9604-127">在添加独立管理单元对话框中，选择**证书**，单击**添加**，单击**关闭**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b9604-127">In the Add Standalone Snap-in dialog box, select **Certificates**, click **Add**, click **Close**, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="b9604-128">在 Microsoft 管理控制台中，展开**证书-当前用户**，右键单击**个人**，指向**所有任务**，然后单击**导入**.</span><span class="sxs-lookup"><span data-stu-id="b9604-128">In Microsoft Management Console, expand **Certificates - Current User**, right-click **Personal**, point to **All Tasks**, and then click **Import**.</span></span>  
  
8. <span data-ttu-id="b9604-129">上**证书导入向导欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b9604-129">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="b9604-130">上**导入的文件**页上，单击**浏览**并找到包含您要导入的证书的.pfx 证书文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b9604-130">On the **File to Import** page, click **Browse** and locate the folder that contains the .pfx certificate file that contains the certificate that you want to import.</span></span> <span data-ttu-id="b9604-131">选择相应的文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="b9604-131">Select the appropriate file, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="b9604-132">上**密码**页上，在**密码**框中，键入私钥文件的密码。</span><span class="sxs-lookup"><span data-stu-id="b9604-132">On the **Password** page, in the **Password** box, type the password for the private-key file.</span></span>  
  
11. <span data-ttu-id="b9604-133">选择**启用强私钥保护**或**标志此密钥为可导出**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b9604-133">Select **Enable strong private key protection** or **Mark this key as exportable**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="b9604-134">上**证书存储区**页上，选择**自动选择基于证书的类型的证书**或**将所有证书都放入下列存储**.</span><span class="sxs-lookup"><span data-stu-id="b9604-134">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="b9604-135">如果选择**将所有证书都放入下列存储**，单击**浏览**，选择在存储区，单击**确定**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b9604-135">If you select **Place all certificates in the following store**, click **Browse**, select the store, click **OK**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="b9604-136">上**正在完成证书导入向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="b9604-136">On the **Completing the Certificate Import Wizard** page, click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9604-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9604-137">See Also</span></span>  
 <span data-ttu-id="b9604-138">[配置使用 MMC 导入的证书](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span><span class="sxs-lookup"><span data-stu-id="b9604-138">[Configuring Certificates Imported Using MMC](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span></span>  
 [<span data-ttu-id="b9604-139">CertWizard</span><span class="sxs-lookup"><span data-stu-id="b9604-139">CertWizard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)