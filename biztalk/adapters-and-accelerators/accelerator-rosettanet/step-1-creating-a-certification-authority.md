---
title: 步骤 1： 创建证书颁发机构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, creating
- double action tutorial, creating certificates
- creating, certificates
ms.assetid: b6ecd534-6b03-4336-8337-33ec18a0802a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d796608a4cc323ccf5e1a8bdee7420c5bab259
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966227"
---
# <a name="step-1-creating-a-certification-authority"></a><span data-ttu-id="ba053-102">步骤 1： 创建证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="ba053-102">Step 1: Creating a Certification Authority</span></span>
<span data-ttu-id="ba053-103">在本主题中，你将安装证书服务 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 组件。</span><span class="sxs-lookup"><span data-stu-id="ba053-103">In this topic, you install the Certificate Services [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] component.</span></span> <span data-ttu-id="ba053-104">并使用该组件生成在 Contoso 组织与 Fabrikam 组织之间进行安全通信所需的证书。</span><span class="sxs-lookup"><span data-stu-id="ba053-104">You use it to generate the certificates that you need to promote secure communication between the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="ba053-105">每个贸易合作伙伴都将拥有一个专用的通信加密证书和一个用于标识身份的专用签名证书。</span><span class="sxs-lookup"><span data-stu-id="ba053-105">Each trading partner will have a private encryption certificate for communication and a private signature certificate for identification purposes.</span></span> <span data-ttu-id="ba053-106">此外，合作伙伴将彼此共享公钥证书，以便在实现 3A2 合作伙伴流程接口 (PIP) 时实现安全通信。</span><span class="sxs-lookup"><span data-stu-id="ba053-106">Additionally, the partners will share their public key certificates with each other to promote secure communication when implementing the 3A2 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-install-the-certificate-server"></a><span data-ttu-id="ba053-107">安装证书服务器</span><span class="sxs-lookup"><span data-stu-id="ba053-107">To install the certificate server</span></span>  
  
1.  <span data-ttu-id="ba053-108">单击**启动**，指向**设置**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="ba053-108">Click **Start**, point to **Settings**, and then click **Control Panel**.</span></span> <span data-ttu-id="ba053-109">双击**添加或删除程序**。</span><span class="sxs-lookup"><span data-stu-id="ba053-109">Double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="ba053-110">在**添加或删除程序**对话框中，单击**添加/删除 Windows 组件**。</span><span class="sxs-lookup"><span data-stu-id="ba053-110">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="ba053-111">上**Windows 组件向导**页上，在**组件**部分中，选择**证书服务**，单击**是**，然后单击**下一步**以启动配置组件向导。</span><span class="sxs-lookup"><span data-stu-id="ba053-111">On the **Windows Components Wizard** page, in the **Components** section, select **Certificate Services**, click **Yes**, and then click **Next** to start the Configuring Components Wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba053-112">如果**证书 ServicesWindows**已选择组件，请跳过此过程的其余部分。</span><span class="sxs-lookup"><span data-stu-id="ba053-112">If the **Certificates ServicesWindows** component is already selected, skip the rest of this procedure.</span></span>  
  
4.  <span data-ttu-id="ba053-113">上**CA 类型**页上，请确保**独立根 CA**已选择，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ba053-113">On the **CA Type** page, make sure that **Stand-alone root CA** is selected, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="ba053-114">上**CA 标识信息**页上，在**此 CA 的常见名称**框中，键入**Contoso FabrikamCA**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ba053-114">On the **CA Identifying Information** page, in the **Common name for this CA** box, type **Contoso-FabrikamCA**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="ba053-115">上**证书数据库设置**页上，保留默认设置，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ba053-115">On the **Certificate Database Settings** page, leave the defaults, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="ba053-116">单击**是**时向导将提示你停止 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="ba053-116">Click **Yes** when the wizard prompts you to stop Internet Information Services (IIS).</span></span>  
  
8.  <span data-ttu-id="ba053-117">单击**是**如果**配置 じ ン 弘艶**会提示你启用 Active Server Pages。</span><span class="sxs-lookup"><span data-stu-id="ba053-117">Click **Yes** if the **Configuring Components Wizard** prompts you to enable Active Server Pages.</span></span>  
  
9. <span data-ttu-id="ba053-118">单击**完成**关闭**Windows 组件向导**。</span><span class="sxs-lookup"><span data-stu-id="ba053-118">Click **Finish** to close the **Windows Components Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba053-119">你只需将一台计算机用作证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="ba053-119">You only have to use one computer as the Certification Authority.</span></span> <span data-ttu-id="ba053-120">而不必在第二台计算机上重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="ba053-120">You do not have to repeat this step on the second computer.</span></span> <span data-ttu-id="ba053-121">本教程将 Contoso 计算机用作证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="ba053-121">This tutorial uses the Contoso computer as the Certification Authority.</span></span>  
  
### <a name="to-install-a-root-certification-authority-ca-for-windows-server-2008"></a><span data-ttu-id="ba053-122">安装 Windows Server 2008 的根证书颁发机构 (CA)</span><span class="sxs-lookup"><span data-stu-id="ba053-122">To install a root Certification Authority (CA) for Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="ba053-123">打开服务器管理器中，单击**添加角色**在角色中，单击**下一步**，然后单击**Active Directory 证书**服务复选框。</span><span class="sxs-lookup"><span data-stu-id="ba053-123">Open Server Manager, click **Add Roles** in Roles, click **Next**, and click **Active Directory Certificate** Services check box.</span></span> <span data-ttu-id="ba053-124">单击**下一步**两次。</span><span class="sxs-lookup"><span data-stu-id="ba053-124">Click **Next** twice.</span></span>  
  
2.  <span data-ttu-id="ba053-125">在选择角色服务页上，单击**证书颁发机构和证书颁发机构 Web 注册**。</span><span class="sxs-lookup"><span data-stu-id="ba053-125">On the Select Role Services page, click **Certification Authority and Certification Authority Web Enrollment**.</span></span> <span data-ttu-id="ba053-126">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="ba053-126">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="ba053-127">在指定安装程序类型页上单击**独立**。</span><span class="sxs-lookup"><span data-stu-id="ba053-127">On the Specify Setup Type page, click **Standalone**.</span></span> <span data-ttu-id="ba053-128">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="ba053-128">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="ba053-129">在“指定 CA 类型”页中，单击“根 CA”。</span><span class="sxs-lookup"><span data-stu-id="ba053-129">On the Specify CA Type page, click Root CA.</span></span> <span data-ttu-id="ba053-130">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="ba053-130">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="ba053-131">在“设置私钥”页上，单击“新建私钥”。</span><span class="sxs-lookup"><span data-stu-id="ba053-131">On the Set Up Private Key page, click Create a new private key.</span></span> <span data-ttu-id="ba053-132">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="ba053-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="ba053-133">在“为 CA 配置加密”页上，</span><span class="sxs-lookup"><span data-stu-id="ba053-133">On the Configure Cryptography for CA page.</span></span> <span data-ttu-id="ba053-134">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="ba053-134">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="ba053-135">配置 CA 名称，在该框 CA 的常见名称中键入 Contoso FabrikamCA，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ba053-135">On Configure CA Name, in the Common name for this CA box, type Contoso-FabrikamCA, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="ba053-136">在设置有效期页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ba053-136">On the Set Validity Period page, click **Next**.</span></span>  
  
9. <span data-ttu-id="ba053-137">在配置证书数据库页中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ba053-137">On the Configure Certificate Database page, Click **Next**.</span></span>  
  
10. <span data-ttu-id="ba053-138">在确认安装选项页上，单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="ba053-138">On the Confirm Installation Options page, click **Install**.</span></span>  
  
### <a name="configuring-the-web-site-for-the-ca-to-use-https-authentication"></a><span data-ttu-id="ba053-139">配置此 CA 的网站以使用 HTTPS 身份验证</span><span class="sxs-lookup"><span data-stu-id="ba053-139">Configuring the Web site for the CA to use HTTPS authentication</span></span>  
  
1.  <span data-ttu-id="ba053-140">在你用作证书颁发机构的计算机上，单击“开始”，指向“所有程序”，再指向“管理工具”，然后单击“Internet 信息服务(IIS)管理器”。</span><span class="sxs-lookup"><span data-stu-id="ba053-140">On the computer you used as the Certification Authority, click Start, point to All Programs, point to Administrative Tools, and then click Internet Information Services (IIS) Manager.</span></span>  
  
2.  <span data-ttu-id="ba053-141">在 Internet 信息服务 (IIS) 管理器对话框中，右键单击**Default Web Site 和选择编辑绑定...**</span><span class="sxs-lookup"><span data-stu-id="ba053-141">In the Internet Information Services (IIS) Manager dialog box, right click **Default Web Site and select Edit Bindings…**</span></span> <span data-ttu-id="ba053-142">从弹出菜单中。</span><span class="sxs-lookup"><span data-stu-id="ba053-142">from the popup menu.</span></span>  
  
3.  <span data-ttu-id="ba053-143">在站点绑定对话框中单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ba053-143">In Site Bindings dialog box click **Add**.</span></span>  
  
4.  <span data-ttu-id="ba053-144">在添加站点绑定对话框中选择**https**类型下拉列表中，选择从证书**SSL 证书**下拉列表中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ba053-144">In Add Site Binding dialog box select **https** in Type drop down, select the certificate from **SSL certificate** drop down and click **OK**.</span></span>  
  
5.  <span data-ttu-id="ba053-145">单击**关闭**以关闭站点绑定...</span><span class="sxs-lookup"><span data-stu-id="ba053-145">Click **Close** to close the Site Bindings…</span></span> <span data-ttu-id="ba053-146">对话框。</span><span class="sxs-lookup"><span data-stu-id="ba053-146">dialog box.</span></span>  
  
### <a name="to-download-the-ca-certificate"></a><span data-ttu-id="ba053-147">下载 CA 证书</span><span class="sxs-lookup"><span data-stu-id="ba053-147">To download the CA certificate</span></span>  
  
1.  <span data-ttu-id="ba053-148">在 Internet Explorer 中，找到并打开 http://<contoso_computername>/certsrv/Default.asp。</span><span class="sxs-lookup"><span data-stu-id="ba053-148">In Internet Explorer, locate and open http://<contoso_computername>/certsrv/Default.asp.</span></span>  
  
2.  <span data-ttu-id="ba053-149">在 Default.asp 页上，单击**下载 CA 证书、 证书链或 CRL**。</span><span class="sxs-lookup"><span data-stu-id="ba053-149">On the Default.asp page, click **Download a CA certificate, certificate chain, or CRL**.</span></span>  
  
3.  <span data-ttu-id="ba053-150">请确保**当前 [Contoso FabrikamCA]** 中选择**CA 证书**列表，，然后单击**下载 CA 证书**。</span><span class="sxs-lookup"><span data-stu-id="ba053-150">Make sure that **Current[Contoso-FabrikamCA]** is selected in the **CA Certificate** list, and then click **Download CA Certificate**.</span></span>  
  
4.  <span data-ttu-id="ba053-151">将该证书保存为 Contoso 和 Fabrikam 计算机上的 C:\Certs\Contoso-FabrikamCA.cer。</span><span class="sxs-lookup"><span data-stu-id="ba053-151">Save the certificate to C:\Certs\Contoso-FabrikamCA.cer on both the Contoso and the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-ca-certificate-to-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="ba053-152">将 CA 证书导入受信任根证书授权机构存储区</span><span class="sxs-lookup"><span data-stu-id="ba053-152">To import the CA certificate to the Trusted Root Certification Authorities store</span></span>  
  
1.  <span data-ttu-id="ba053-153">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ba053-153">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="ba053-154">在命令提示符下，将移到**\<驱动器\>: \Program Files\MicrosoftBizTalk\<版本\>Accelerator for RosettaNet\SDK**，然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="ba053-154">At the command prompt, move to **\<drive\>:\Program Files\MicrosoftBizTalk \<version\> Accelerator for RosettaNet\SDK**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="ba053-155">在命令提示符处，键入**CertWizard /Rootkey"\<驱动器\>: \Certs\Contoso-FabrikamCA.cer"**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="ba053-155">At the command prompt, type **CertWizard /Rootkey "\<drive\>:\Certs\Contoso-FabrikamCA.cer"**, and then press **Enter**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ba053-156">此步骤在 Contoso 和 Fabrikam 计算机上都要执行。</span><span class="sxs-lookup"><span data-stu-id="ba053-156">Perform this procedure on both the Contoso and Fabrikam computers.</span></span>  
  
### <a name="to-enable-automatic-certificate-issuing"></a><span data-ttu-id="ba053-157">启用自动颁发证书</span><span class="sxs-lookup"><span data-stu-id="ba053-157">To enable automatic certificate issuing</span></span>  
  
1.  <span data-ttu-id="ba053-158">在用作证书颁发机构的计算机，单击**启动**，指向**程序**，指向**管理工具**，然后单击**证书颁发机构**。</span><span class="sxs-lookup"><span data-stu-id="ba053-158">On the computer you used as the Certification Authority, click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Certification Authority**.</span></span>  
  
2.  <span data-ttu-id="ba053-159">在证书颁发机构对话框中，右键单击**Contoso FabrikamCA**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ba053-159">In the Certification Authority dialog box, right-click **Contoso-FabrikamCA**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ba053-160">在 Contoso FabrikamCA 属性对话框中，在**策略模块**选项卡上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ba053-160">In the Contoso-FabrikamCA Properties dialog box, on the **Policy Module** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ba053-161">在属性对话框中，选择 **，按照中的证书模板设置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ba053-161">In the Properties dialog box, select **Follow the settings in the certificate template**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ba053-162">单击**确定**以关闭 Contoso FabrikamCA 对话框。</span><span class="sxs-lookup"><span data-stu-id="ba053-162">Click **OK** to close the Contoso-FabrikamCA dialog box.</span></span>  
  
6.  <span data-ttu-id="ba053-163">关闭“证书颁发机构”对话框。</span><span class="sxs-lookup"><span data-stu-id="ba053-163">Close the Certification Authority dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba053-164">通过启用自动颁发证书，证书服务可将证书颁发过程自动化。</span><span class="sxs-lookup"><span data-stu-id="ba053-164">By enabling automatic certificate issuing, Certificate Services automates the certificate issuing procedure.</span></span> <span data-ttu-id="ba053-165">必须重新启动证书服务才能应用此更改。</span><span class="sxs-lookup"><span data-stu-id="ba053-165">You will have to restart Certificate Services to apply this change.</span></span>  
    >   
    >  <span data-ttu-id="ba053-166">你可能需要将根证书 Contoso-FabrikamCA.cer 安装在 Current User\Trusted Root Certification authorities 中。</span><span class="sxs-lookup"><span data-stu-id="ba053-166">You may need to install the Root Certificate Contoso-FabrikamCA.cer in the Current User\Trusted Root Certification authorities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba053-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba053-167">See Also</span></span>  
 [<span data-ttu-id="ba053-168">步骤 2：创建公共和私有证书</span><span class="sxs-lookup"><span data-stu-id="ba053-168">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)