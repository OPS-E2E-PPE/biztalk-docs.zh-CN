---
title: "步骤 4： 启用安全套接字在 IIS 中的层 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Secure Socket Layers
- IIS
- double action tutorial, enabling SSL in IIS
- SSL
ms.assetid: 96109294-595a-46ac-974e-33123df79ed5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2964b6ac26d6685a1c38b88c5bbf98e8119f3502
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-4-enabling-secure-sockets-layer-in-iis"></a><span data-ttu-id="c181d-102">步骤 4： 启用安全套接字在 IIS 中的层</span><span class="sxs-lookup"><span data-stu-id="c181d-102">Step 4: Enabling Secure Sockets Layer in IIS</span></span>
<span data-ttu-id="c181d-103">安全套接字层 (SSL) 是一个协议，旨在增强客户端与服务器之间通信通道的安全性。</span><span class="sxs-lookup"><span data-stu-id="c181d-103">Secure Sockets Layer (SSL) is a protocol designed to secure the communication channel between a client and a server.</span></span> <span data-ttu-id="c181d-104">通过在 Microsoft® Internet 信息服务 (IIS) 7.5/7.0 中启用 SSL，Contoso 和 Fabrikam 组织在通信中对所有的数据传输使用身份验证和加密。</span><span class="sxs-lookup"><span data-stu-id="c181d-104">By enabling SSL in Microsoft® Internet Information Services (IIS) 7.5/7.0, the Contoso and Fabrikam organizations communicate using authentication and encryption for all data transfers.</span></span> <span data-ttu-id="c181d-105">在此步骤中，您将学习如何在 IIS 7.5/7.0 中启用 SSL。</span><span class="sxs-lookup"><span data-stu-id="c181d-105">In this step, you learn how to enable SSL in IIS 7.5/7.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c181d-106">在 Contoso 和 Fabrikam 计算机上都必须执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="c181d-106">You have to perform this step on both the Contoso and Fabrikam computers.</span></span>  
  
### <a name="to-prepare-a-new-server-certificate"></a><span data-ttu-id="c181d-107">准备新服务器证书</span><span class="sxs-lookup"><span data-stu-id="c181d-107">To prepare a new server certificate</span></span>  
  
1.  <span data-ttu-id="c181d-108">单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="c181d-108">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="c181d-109">在 Internet Information Services 的左窗格中，展开 **\<**  *computer_name*  **\>**  (*本地计算机*)，展开**网站**，右键单击**Default Web Site**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c181d-109">In the Internet Information Services left pane, expand **\<***computer_name***\>** (*local computer*), expand **Web Sites**, right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c181d-110">在默认网站对话框中，在**目录安全性**选项卡上，单击**服务器证书**启动**IIS 证书向导**。</span><span class="sxs-lookup"><span data-stu-id="c181d-110">In the Default Web Sites dialog box, on the **Directory Security** tab, click **Server Certificate** to start the **IIS Certificate Wizard**.</span></span>  
  
4.  <span data-ttu-id="c181d-111">上**欢迎使用 Web 服务器证书向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-111">On the **Welcome to the Web Server Certificate Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="c181d-112">上**服务器证书**页上，选择**创建新证书**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-112">On the **Server Certificate** page, select **Create a new certificate**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="c181d-113">上**延迟或立即请求**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-113">On the **Delayed or immediate request** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="c181d-114">上**名称和安全设置**页上，单击**下一步**，保留默认值。</span><span class="sxs-lookup"><span data-stu-id="c181d-114">On the **Name and Security Settings** page, click **Next**, keeping the defaults.</span></span>  
  
8.  <span data-ttu-id="c181d-115">上**组织信息**页上，在**组织**框中，键入**Contoso**如果已打开 Contoso 计算机或**Fabrikam**如果已打开Fabrikam 计算机，请在**组织单位**框中，键入**测试**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-115">On the **Organization Information** page, in the **Organization** box, type **Contoso** if on the Contoso computer or **Fabrikam** if on the Fabrikam computer, in the **Organizational unit** box, type **Test**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="c181d-116">上**站点的公用名称**页上，在**公用名**框中，键入你的计算机的名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-116">On the **Your Site's Common Name** page, in the **Common name** box, type the name of your computer, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="c181d-117">上**的地理位置信息**页上，在**省/市/自治区**框中，键入你省自治区直辖市**城市/地点**框中，键入你城市/地点，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-117">On the **Geographical Information** page, in the **State/province** box, type your state/province, in the **City/locality** box, type your city/locality, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="c181d-118">上**证书请求文件名称**页上，在**文件名**框中，保留默认值**C:\certreq.txt**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-118">On the **Certificate Request File Name** page, in the **File name** box, leave the default **C:\certreq.txt**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="c181d-119">上**请求文件摘要**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-119">On the **Request File Summary** page, click **Next**.</span></span>  
  
13. <span data-ttu-id="c181d-120">上**完成 Web 服务器证书向导**页上，单击**完成**关闭**IIS 证书向导**。</span><span class="sxs-lookup"><span data-stu-id="c181d-120">On the **Completing the Web Server Certificate Wizard** page, click **Finish** to close the **IIS Certificate Wizard**.</span></span>  
  
### <a name="to-generate-a-new-server-certificate"></a><span data-ttu-id="c181d-121">生成新服务器证书</span><span class="sxs-lookup"><span data-stu-id="c181d-121">To generate a new server certificate</span></span>  
  
1.  <span data-ttu-id="c181d-122">在 Internet Explorer 中，找到并打开 http://\<*contoso_machine*\>/CertSrv。</span><span class="sxs-lookup"><span data-stu-id="c181d-122">In Internet Explorer, locate and open http://\<*contoso_machine*\>/CertSrv.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c181d-123">在步骤 1 中，打开 http://\<*contoso_machine*\>/CertSrv Contoso 或 Fabrikam 计算机上的。</span><span class="sxs-lookup"><span data-stu-id="c181d-123">In step 1, open http://\<*contoso_machine*\>/CertSrv on the Contoso or Fabrikam computer.</span></span>  
  
2.  <span data-ttu-id="c181d-124">上**Microsoft 证书服务向导欢迎**页上，单击**请求证书。**</span><span class="sxs-lookup"><span data-stu-id="c181d-124">On the **Microsoft Certificate Services Wizard Welcome** page, click **Request a certificate.**</span></span>  
  
3.  <span data-ttu-id="c181d-125">上**请求证书**页上，单击**高级的证书申请**。</span><span class="sxs-lookup"><span data-stu-id="c181d-125">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  
  
4.  <span data-ttu-id="c181d-126">上**高级证书申请**页上，单击**提交证书申请的步骤使用 base 64 编码 CMC 或 PKCS #10 文件，或使用 base 64 编码的 PKCS #7 文件提交续订申请**。</span><span class="sxs-lookup"><span data-stu-id="c181d-126">On the **Advanced Certificate Request** page, click **Submit a certificate request by using a base-64-encoded CMC or PKCS #10 file, or submit a renewal request by using a base-64-encoded PKCS #7 file**.</span></span>  
  
5.  <span data-ttu-id="c181d-127">上**提交证书请求或续订请求**页上，单击**浏览要插入的文件**。</span><span class="sxs-lookup"><span data-stu-id="c181d-127">On the **Submit a Certificate Request or Renewal Request** page, click **Browse for a file to insert**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c181d-128">如果单击该链接时，你可以收到安全错误，在记事本或其他文本编辑器中打开文件 C:\certreq.txt、 复制文件的内容，并将该信息粘贴**保存请求**框中，并依次**提交**。</span><span class="sxs-lookup"><span data-stu-id="c181d-128">If you receive a security error when clicking the link, open the file C:\certreq.txt in Notepad or another text editor, copy the contents of the file and paste that information in the **Saved Request** box, and then click **Submit**.</span></span> <span data-ttu-id="c181d-129">然后即可执行步骤 10。</span><span class="sxs-lookup"><span data-stu-id="c181d-129">You can then go to step 10.</span></span>  
  
6.  <span data-ttu-id="c181d-130">单击**浏览**以打开**选择文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="c181d-130">Click **Browse** to open the **Choose File** dialog box.</span></span>  
  
7.  <span data-ttu-id="c181d-131">在**选择文件**对话框中，找到*\<驱动器\>*: \ 文件夹中，选择 certreq.txt 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="c181d-131">In the **Choose File** dialog box, locate the *\<drive\>*:\ folder, select the certreq.txt file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="c181d-132">上**提交证书请求或续订请求**页上，单击**读取**。</span><span class="sxs-lookup"><span data-stu-id="c181d-132">On the **Submit a Certificate Request or Renewal Request** page, click **Read**.</span></span>  
  
9. <span data-ttu-id="c181d-133">上**提交证书请求或续订请求**页上，单击**提交**来生成新证书。</span><span class="sxs-lookup"><span data-stu-id="c181d-133">On the **Submit a Certificate Request or Renewal Request** page, click **Submit** to generate the new certificate.</span></span>  
  
10. <span data-ttu-id="c181d-134">上**颁发证书**页上，单击**下载证书**。</span><span class="sxs-lookup"><span data-stu-id="c181d-134">On the **Certificate Issued** page, click **Download Certificate**.</span></span>  
  
11. <span data-ttu-id="c181d-135">在**文件下载**对话框中，单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c181d-135">In the **File Download** dialog box, click **Save**.</span></span>  
  
12. <span data-ttu-id="c181d-136">在**另存为**对话框中，保存到证书\<驱动器\>: \Certs\SSLCert.cer，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c181d-136">In the **Save As** dialog box, save the certificate to \<drive\>:\Certs\SSLCert.cer, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="c181d-137">单击**关闭**关闭**下载已完成**对话框。</span><span class="sxs-lookup"><span data-stu-id="c181d-137">Click **Close** to close the **Download Complete** dialog box.</span></span>  
  
### <a name="to-prepare-a-new-server-certificate-for-iis"></a><span data-ttu-id="c181d-138">为 IIS 准备新服务器证书</span><span class="sxs-lookup"><span data-stu-id="c181d-138">To Prepare a new Server Certificate for IIS</span></span>  
  
1.  <span data-ttu-id="c181d-139">单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="c181d-139">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="c181d-140">在 Internet Information Services 的左窗格中，单击 < 计算机名 > （本地计算机），双击**服务器证书**右窗格中。</span><span class="sxs-lookup"><span data-stu-id="c181d-140">In the Internet Information Services left pane, click <computer_name> (local computer), double click **Server Certificates** in the right pane.</span></span> <span data-ttu-id="c181d-141">选择**创建证书请求**从操作窗格。</span><span class="sxs-lookup"><span data-stu-id="c181d-141">Select **Create Certificate Request** from Actions pane.</span></span>  
  
3.  <span data-ttu-id="c181d-142">可分辨名称属性对话框中键入的公用名中的计算机的名称： 文本框中，组织中： 框中，键入**Contoso**如果已打开 Contoso 计算机或**Fabrikam**如果已打开 Fabrikam计算机上的组织单位： 框中，键入测试，请在城市/地点框中，省/市/自治区框中键入你城市/地点，、 键入中的国家/地区下拉列表，选择你省自治区直辖市国家/地区，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="c181d-142">In Distinguished Name Properties dialog box type the name of the computer in the Common name: text box, in the Organization: box, type **Contoso** if on the Contoso computer or **Fabrikam** if on the Fabrikam computer, in the Organizational unit: box type Test, in the City/locality box, type your city/locality, in the State/province box, type your state/province, in the Country/region drop down, select your Country/region and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="c181d-143">在加密服务提供程序属性对话框中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-143">In the Cryptographic Service Provider Properties dialog box, click **Next**.</span></span>  
  
5.  <span data-ttu-id="c181d-144">在文件名对话框中，在文本框中，指定 C:\certreq.txt 单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="c181d-144">In the File Name dialog box, specify C:\certreq.txt in the text box, click **Finish**.</span></span>  
  
### <a name="to-generate-a-new-server-certificate-for-iis"></a><span data-ttu-id="c181d-145">为 IIS 生成新服务器证书</span><span class="sxs-lookup"><span data-stu-id="c181d-145">To generate a new server certificate for IIS</span></span>  
  
1.  <span data-ttu-id="c181d-146">在 Internet Explorer 中，找到并打开 http://<contoso_machine>/CertSrv。</span><span class="sxs-lookup"><span data-stu-id="c181d-146">In Internet Explorer, locate and open http://<contoso_machine>/CertSrv.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c181d-147">在步骤 1 中，打开 Contoso 或 Fabrikam 计算机上的 http://<contoso_machine>/CertSrv。</span><span class="sxs-lookup"><span data-stu-id="c181d-147">In step 1, open http://<contoso_machine>/CertSrv on the Contoso or Fabrikam computer.</span></span>  
  
2.  <span data-ttu-id="c181d-148">在 Microsoft 证书服务向导欢迎页上，单击**请求证书**。</span><span class="sxs-lookup"><span data-stu-id="c181d-148">On the Microsoft Certificate Services Wizard Welcome page, click **Request a certificate**.</span></span>  
  
3.  <span data-ttu-id="c181d-149">在请求证书页中，单击**高级证书申请**。</span><span class="sxs-lookup"><span data-stu-id="c181d-149">On the Request a Certificate page, click **Advanced Certificate Request**.</span></span>  
  
4.  <span data-ttu-id="c181d-150">在高级证书申请页上，单击**提交证书申请**通过使用 base 64 编码 CMC 或 PKCS #10 文件，或使用 base 64 编码的 PKCS #7 文件提交续订申请。</span><span class="sxs-lookup"><span data-stu-id="c181d-150">On the Advanced Certificate Request page, click **Submit a certificate request** by using a base-64-encoded CMC or PKCS #10 file, or submit a renewal request by using a base-64-encoded PKCS #7 file.</span></span>  
  
5.  <span data-ttu-id="c181d-151">在记事本或其他文本编辑器中打开文件 C:\certreq.txt，复制文件的内容并将该信息粘贴**保存请求**框上提交证书请求，或续订请求的页上，并依次**提交**。</span><span class="sxs-lookup"><span data-stu-id="c181d-151">Open the file C:\certreq.txt in Notepad or another text editor, copy the contents of the file and paste that information in the **Saved Request** box on the Submit a Certificate Request or Renewal Request page, and then click **Submit**.</span></span>  
  
6.  <span data-ttu-id="c181d-152">在证书颁发页上，单击**下载证书**。</span><span class="sxs-lookup"><span data-stu-id="c181d-152">On the Certificate Issued page, click **Download Certificate**.</span></span>  
  
7.  <span data-ttu-id="c181d-153">在文件下载对话框中，单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c181d-153">In the File Download dialog box, click **Save**.</span></span>  
  
8.  <span data-ttu-id="c181d-154">在另存为对话框中，将保存到证书\<驱动器\>: \Certs\SSLCert.cer，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c181d-154">In the Save As dialog box, save the certificate to \<drive\>:\Certs\SSLCert.cer, and then click **Save**.</span></span>  
  
### <a name="to-import-the-server-certificate-into-iis"></a><span data-ttu-id="c181d-155">将服务器证书导入 IIS</span><span class="sxs-lookup"><span data-stu-id="c181d-155">To import the server certificate into IIS</span></span>  
  
1.  <span data-ttu-id="c181d-156">单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="c181d-156">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="c181d-157">在 Internet Information Services 的左窗格中，单击**（本地计算机）**，双击**服务器证书**右窗格中。</span><span class="sxs-lookup"><span data-stu-id="c181d-157">In the Internet Information Services left pane, click **(local computer)**, double click **Server Certificates** in the right pane.</span></span> <span data-ttu-id="c181d-158">选择**完成证书请求**从操作窗格。</span><span class="sxs-lookup"><span data-stu-id="c181d-158">Select **Complete Certificate Request** from the Actions pane.</span></span>  
  
3.  <span data-ttu-id="c181d-159">在指定的证书颁发机构响应对话框框中键入**\<驱动器\>: \Certs\SSLCert.cer**中**包含证书颁发机构的响应文件的名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="c181d-159">In Specify Certificate Authority Response dialog box type **\<drive\>:\Certs\SSLCert.cer** in **File name containing the certification authority’s response** text box.</span></span> <span data-ttu-id="c181d-160">中的友好名称文本框中键入**ContosoSSLCert**。</span><span class="sxs-lookup"><span data-stu-id="c181d-160">In Friendly name text box type **ContosoSSLCert**.</span></span>  
  
### <a name="to-enable-ssl-bindings-for-iis"></a><span data-ttu-id="c181d-161">为 IIS 启用 SSL 绑定</span><span class="sxs-lookup"><span data-stu-id="c181d-161">To enable SSL bindings for IIS</span></span>  
  
1.  <span data-ttu-id="c181d-162">单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="c181d-162">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="c181d-163">在 Internet Information Services 的左窗格中，展开**（本地计算机）**，展开**站点**，右键单击**Default Web Site**，然后单击**编辑绑定**。</span><span class="sxs-lookup"><span data-stu-id="c181d-163">In the Internet Information Services left pane, expand **(local computer)**, expand **Sites**, right-click **Default Web Site**, and then click **Edit Bindings**.</span></span>  
  
3.  <span data-ttu-id="c181d-164">在站点绑定对话框中单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="c181d-164">In Site Bindings dialog box click **Add**.</span></span> <span data-ttu-id="c181d-165">在添加网站绑定对话框中选择**https**从类型下拉列表中，选择**ContosoSSLCert**从 SSL 证书下拉列表中，单击**确定**，单击**关闭**.</span><span class="sxs-lookup"><span data-stu-id="c181d-165">In the Add Site Binding dialog box select **https** from Type drop down, select **ContosoSSLCert** from SSL certificate drop down, click **OK**, click **Close**.</span></span>  
  
### <a name="to-import-the-server-certificate-into-iis"></a><span data-ttu-id="c181d-166">将服务器证书导入 IIS</span><span class="sxs-lookup"><span data-stu-id="c181d-166">To import the server certificate into IIS</span></span>  
  
1.  <span data-ttu-id="c181d-167">单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="c181d-167">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="c181d-168">在 Internet Information Services 的左窗格中，展开 **\<**  *computer_name* \> (*本地计算机*)，展开**Web站点**，右键单击**Default Web Site**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c181d-168">In the Internet Information Services left pane, expand **\<***computer_name*\> (*local computer*), expand **Web Sites**, right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c181d-169">在默认 Web 站点属性对话框中，在**目录安全性**选项卡上，单击**服务器证书**启动**IIS 证书向导**。</span><span class="sxs-lookup"><span data-stu-id="c181d-169">In the Default Web Site Properties dialog box, on the **Directory Security** tab, click **Server Certificate** to start the **IIS Certificate Wizard**.</span></span>  
  
4.  <span data-ttu-id="c181d-170">上**欢迎使用 Web 服务器证书向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-170">On the **Welcome to the Web Server Certificate Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="c181d-171">上**挂起的证书申请**页上，选择**处理挂起的请求和安装证书**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-171">On the **Pending Certificate Request** page, select **Process the pending request and install the certificate**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="c181d-172">上**处理挂起的请求**页上，在**路径和文件名**框中，键入**\<驱动器\>: \Certs\SSLCert.cer** （或浏览到该文件）然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-172">On the **Process a Pending Request** page, in the **Path and file name** box, type **\<drive\>:\Certs\SSLCert.cer** (or browse to that file) and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="c181d-173">上**SSL 端口页**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-173">On the **SSL Port page**, click **Next**.</span></span>  
  
8.  <span data-ttu-id="c181d-174">上**证书摘要**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c181d-174">On the **Certificate Summary** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="c181d-175">上**完成 Web 服务器证书向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="c181d-175">On the **Completing the Web Server Certificate Wizard** page, click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c181d-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c181d-176">See Also</span></span>  
 [<span data-ttu-id="c181d-177">创建和配置 Contoso 解决方案</span><span class="sxs-lookup"><span data-stu-id="c181d-177">Creating and Configuring the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)