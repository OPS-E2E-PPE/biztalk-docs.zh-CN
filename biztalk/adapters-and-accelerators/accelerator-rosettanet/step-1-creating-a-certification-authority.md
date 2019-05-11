---
title: 第 1 步：创建证书颁发机构 |Microsoft Docs
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
ms.openlocfilehash: adbcc42cc358b6aa370f1c7ba0ba62d4caee2d9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281559"
---
# <a name="step-1-creating-a-certification-authority"></a><span data-ttu-id="7a4d7-102">第 1 步：创建证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="7a4d7-102">Step 1: Creating a Certification Authority</span></span>
<span data-ttu-id="7a4d7-103">在本主题中，安装证书服务[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]组件。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-103">In this topic, you install the Certificate Services [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] component.</span></span> <span data-ttu-id="7a4d7-104">用于生成在你需要升级 Contoso 和 Fabrikam 组织之间进行安全通信的证书。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-104">You use it to generate the certificates that you need to promote secure communication between the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="7a4d7-105">每个贸易合作伙伴将具有用于通信的专用加密证书和身份标识的专用签名证书。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-105">Each trading partner will have a private encryption certificate for communication and a private signature certificate for identification purposes.</span></span> <span data-ttu-id="7a4d7-106">此外，合作伙伴将共享与其他实现 3A2 合作伙伴接口流程 (PIP) 时升级安全通信的公钥证书。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-106">Additionally, the partners will share their public key certificates with each other to promote secure communication when implementing the 3A2 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-install-the-certificate-server"></a><span data-ttu-id="7a4d7-107">若要安装证书服务器</span><span class="sxs-lookup"><span data-stu-id="7a4d7-107">To install the certificate server</span></span>  
  
1.  <span data-ttu-id="7a4d7-108">单击**启动**，依次指向**设置**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-108">Click **Start**, point to **Settings**, and then click **Control Panel**.</span></span> <span data-ttu-id="7a4d7-109">双击**添加或删除程序**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-109">Double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="7a4d7-110">在中**添加或删除程序**对话框中，单击**添加/删除 Windows 组件**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-110">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="7a4d7-111">上**Windows 组件向导**页上，在**组件**部分中，选择**证书服务**，单击**是**，然后单击**下一步**以启动配置组件向导。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-111">On the **Windows Components Wizard** page, in the **Components** section, select **Certificate Services**, click **Yes**, and then click **Next** to start the Configuring Components Wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a4d7-112">如果**证书服务 Windows**组件已被选定，跳过此过程的其余部分。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-112">If the **Certificates ServicesWindows** component is already selected, skip the rest of this procedure.</span></span>  
  
4.  <span data-ttu-id="7a4d7-113">上**CA 类型**页上，请确保**独立根 CA**已选择，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-113">On the **CA Type** page, make sure that **Stand-alone root CA** is selected, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="7a4d7-114">上**CA 标识信息**页上，在**该 CA 的公用名**框中，键入**Contoso-fabrikamca**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-114">On the **CA Identifying Information** page, in the **Common name for this CA** box, type **Contoso-FabrikamCA**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="7a4d7-115">上**证书数据库设置**页上，保留默认值，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-115">On the **Certificate Database Settings** page, leave the defaults, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="7a4d7-116">单击**是**时向导将提示你停止 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-116">Click **Yes** when the wizard prompts you to stop Internet Information Services (IIS).</span></span>  
  
8.  <span data-ttu-id="7a4d7-117">单击**是**如果**配置组件向导**会提示你启用 Active Server Pages。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-117">Click **Yes** if the **Configuring Components Wizard** prompts you to enable Active Server Pages.</span></span>  
  
9. <span data-ttu-id="7a4d7-118">单击**完成**以关闭**Windows 组件向导**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-118">Click **Finish** to close the **Windows Components Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a4d7-119">只需一台计算机用作证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-119">You only have to use one computer as the Certification Authority.</span></span> <span data-ttu-id="7a4d7-120">不需要第二台计算机上重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-120">You do not have to repeat this step on the second computer.</span></span> <span data-ttu-id="7a4d7-121">本教程将 Contoso 计算机用作证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-121">This tutorial uses the Contoso computer as the Certification Authority.</span></span>  
  
### <a name="to-install-a-root-certification-authority-ca-for-windows-server-2008"></a><span data-ttu-id="7a4d7-122">若要安装适用于 Windows Server 2008 的根证书颁发机构 (CA)</span><span class="sxs-lookup"><span data-stu-id="7a4d7-122">To install a root Certification Authority (CA) for Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="7a4d7-123">打开服务器管理器中，单击**添加角色**在角色中，单击**下一步**，然后单击**Active Directory 证书**Services 复选框。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-123">Open Server Manager, click **Add Roles** in Roles, click **Next**, and click **Active Directory Certificate** Services check box.</span></span> <span data-ttu-id="7a4d7-124">单击**下一步**两次。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-124">Click **Next** twice.</span></span>  
  
2.  <span data-ttu-id="7a4d7-125">在选择角色服务页上，单击**证书颁发机构和证书颁发机构 Web 注册**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-125">On the Select Role Services page, click **Certification Authority and Certification Authority Web Enrollment**.</span></span> <span data-ttu-id="7a4d7-126">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-126">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="7a4d7-127">在指定安装类型页上，单击**独立**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-127">On the Specify Setup Type page, click **Standalone**.</span></span> <span data-ttu-id="7a4d7-128">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-128">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="7a4d7-129">在指定 CA 类型页上，单击根 CA。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-129">On the Specify CA Type page, click Root CA.</span></span> <span data-ttu-id="7a4d7-130">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-130">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="7a4d7-131">在设置私钥页上，单击创建新的私钥。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-131">On the Set Up Private Key page, click Create a new private key.</span></span> <span data-ttu-id="7a4d7-132">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7a4d7-133">在 CA 页配置加密。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-133">On the Configure Cryptography for CA page.</span></span> <span data-ttu-id="7a4d7-134">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-134">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="7a4d7-135">配置 CA 名称，在该框 CA 的公用名中键入 Contoso-fabrikamca，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-135">On Configure CA Name, in the Common name for this CA box, type Contoso-FabrikamCA, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="7a4d7-136">在设置有效期页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-136">On the Set Validity Period page, click **Next**.</span></span>  
  
9. <span data-ttu-id="7a4d7-137">在配置证书数据库页上单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-137">On the Configure Certificate Database page, Click **Next**.</span></span>  
  
10. <span data-ttu-id="7a4d7-138">在确认安装选项页上，单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-138">On the Confirm Installation Options page, click **Install**.</span></span>  
  
### <a name="configuring-the-web-site-for-the-ca-to-use-https-authentication"></a><span data-ttu-id="7a4d7-139">配置 CA 以使用 HTTPS 身份验证网站</span><span class="sxs-lookup"><span data-stu-id="7a4d7-139">Configuring the Web site for the CA to use HTTPS authentication</span></span>  
  
1.  <span data-ttu-id="7a4d7-140">在用作证书颁发机构的计算机，单击开始、 指向所有程序、 都指向管理工具，然后单击 Internet 信息服务 (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-140">On the computer you used as the Certification Authority, click Start, point to All Programs, point to Administrative Tools, and then click Internet Information Services (IIS) Manager.</span></span>  
  
2.  <span data-ttu-id="7a4d7-141">在 Internet 信息服务 (IIS) 管理器对话框中，右键单击**Default Web Site 和选择编辑绑定...**</span><span class="sxs-lookup"><span data-stu-id="7a4d7-141">In the Internet Information Services (IIS) Manager dialog box, right click **Default Web Site and select Edit Bindings…**</span></span> <span data-ttu-id="7a4d7-142">从弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-142">from the popup menu.</span></span>  
  
3.  <span data-ttu-id="7a4d7-143">在站点绑定对话框中单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-143">In Site Bindings dialog box click **Add**.</span></span>  
  
4.  <span data-ttu-id="7a4d7-144">在添加网站绑定对话框中选择**https**类型下拉列表中，选择从证书**SSL 证书**下拉列表中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-144">In Add Site Binding dialog box select **https** in Type drop down, select the certificate from **SSL certificate** drop down and click **OK**.</span></span>  
  
5.  <span data-ttu-id="7a4d7-145">单击**关闭**关闭网站绑定...</span><span class="sxs-lookup"><span data-stu-id="7a4d7-145">Click **Close** to close the Site Bindings…</span></span> <span data-ttu-id="7a4d7-146">对话框。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-146">dialog box.</span></span>  
  
### <a name="to-download-the-ca-certificate"></a><span data-ttu-id="7a4d7-147">若要下载的 CA 证书</span><span class="sxs-lookup"><span data-stu-id="7a4d7-147">To download the CA certificate</span></span>  
  
1.  <span data-ttu-id="7a4d7-148">在 Internet Explorer 中，找到并打开 http://<contoso_computername>/certsrv/Default.asp。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-148">In Internet Explorer, locate and open http://<contoso_computername>/certsrv/Default.asp.</span></span>  
  
2.  <span data-ttu-id="7a4d7-149">在 Default.asp 页上，单击**下载 CA 证书、 证书链或 CRL**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-149">On the Default.asp page, click **Download a CA certificate, certificate chain, or CRL**.</span></span>  
  
3.  <span data-ttu-id="7a4d7-150">请确保**当前 [Contoso-fabrikamca]** 中选择**CA 证书**列表，，然后单击**下载 CA 证书**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-150">Make sure that **Current[Contoso-FabrikamCA]** is selected in the **CA Certificate** list, and then click **Download CA Certificate**.</span></span>  
  
4.  <span data-ttu-id="7a4d7-151">将证书保存到 C:\Certs\Contoso-FabrikamCA.cer，Contoso 和 Fabrikam 计算机上。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-151">Save the certificate to C:\Certs\Contoso-FabrikamCA.cer on both the Contoso and the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-ca-certificate-to-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="7a4d7-152">CA 证书导入到受信任的根证书颁发机构存储区</span><span class="sxs-lookup"><span data-stu-id="7a4d7-152">To import the CA certificate to the Trusted Root Certification Authorities store</span></span>  
  
1.  <span data-ttu-id="7a4d7-153">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-153">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7a4d7-154">在命令提示符处，转到**\<驱动器\>: \Program Files\MicrosoftBizTalk\<版本\>Accelerator for RosettaNet\SDK**，然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="7a4d7-154">At the command prompt, move to **\<drive\>:\Program Files\MicrosoftBizTalk \<version\> Accelerator for RosettaNet\SDK**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="7a4d7-155">在命令提示符处，键入**CertWizard /Rootkey"\<驱动器\>: \Certs\Contoso-FabrikamCA.cer"**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-155">At the command prompt, type **CertWizard /Rootkey "\<drive\>:\Certs\Contoso-FabrikamCA.cer"**, and then press **Enter**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7a4d7-156">Contoso 和 Fabrikam 计算机上执行此过程。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-156">Perform this procedure on both the Contoso and Fabrikam computers.</span></span>  
  
### <a name="to-enable-automatic-certificate-issuing"></a><span data-ttu-id="7a4d7-157">若要启用自动颁发证书</span><span class="sxs-lookup"><span data-stu-id="7a4d7-157">To enable automatic certificate issuing</span></span>  
  
1.  <span data-ttu-id="7a4d7-158">在用作证书颁发机构的计算机，单击**启动**，依次指向**程序**，指向**管理工具**，然后单击**证书颁发机构**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-158">On the computer you used as the Certification Authority, click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Certification Authority**.</span></span>  
  
2.  <span data-ttu-id="7a4d7-159">在证书颁发机构对话框中，右键单击**Contoso-fabrikamca**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-159">In the Certification Authority dialog box, right-click **Contoso-FabrikamCA**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7a4d7-160">在 Contoso-fabrikamca 属性对话框中，在**策略模块**选项卡上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-160">In the Contoso-FabrikamCA Properties dialog box, on the **Policy Module** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7a4d7-161">在属性对话框中，选择 **，按照证书模板中的设置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-161">In the Properties dialog box, select **Follow the settings in the certificate template**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="7a4d7-162">单击**确定**以关闭 Contoso-fabrikamca 对话框。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-162">Click **OK** to close the Contoso-FabrikamCA dialog box.</span></span>  
  
6.  <span data-ttu-id="7a4d7-163">关闭证书颁发机构对话框。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-163">Close the Certification Authority dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a4d7-164">通过启用自动颁发证书，证书服务会自动将证书颁发过程。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-164">By enabling automatic certificate issuing, Certificate Services automates the certificate issuing procedure.</span></span> <span data-ttu-id="7a4d7-165">你将需要重新启动证书服务才能应用此更改。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-165">You will have to restart Certificate Services to apply this change.</span></span>  
    >   
    >  <span data-ttu-id="7a4d7-166">您可能需要根证书 Contoso-fabrikamca.cer 安装在 Current User\Trusted Root Certification 颁发机构。</span><span class="sxs-lookup"><span data-stu-id="7a4d7-166">You may need to install the Root Certificate Contoso-FabrikamCA.cer in the Current User\Trusted Root Certification authorities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a4d7-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a4d7-167">See Also</span></span>  
 [<span data-ttu-id="7a4d7-168">步骤 2：创建公用和私用证书</span><span class="sxs-lookup"><span data-stu-id="7a4d7-168">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)