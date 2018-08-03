---
title: 步骤 2： 创建公用和私用证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating certificates
- public certificates
- certificates, public certificates
- creating, certificates
- private certificates
ms.assetid: 0a925d89-03d9-41fe-907b-85a6ae42362a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f31d1bb1dcc5a0e6f587797f41e97d16ca6606da
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007606"
---
# <a name="step-2-creating-public-and-private-certificates"></a><span data-ttu-id="251ec-102">步骤 2： 创建公用和私用证书</span><span class="sxs-lookup"><span data-stu-id="251ec-102">Step 2: Creating Public and Private Certificates</span></span>
<span data-ttu-id="251ec-103">在此步骤中，使用证书颁发机构中创建[步骤 1： 创建证书颁发机构&#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)以生成 Contoso 和 Fabrikam 组织使用的公钥和私钥证书。</span><span class="sxs-lookup"><span data-stu-id="251ec-103">In this step, you use the Certification Authority created in [Step 1: Creating a Certification Authority &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) to generate the public and private certificates that the Contoso and Fabrikam organizations use.</span></span>  

### <a name="to-generate-the-contoso-and-fabrikam-encryption-certificates"></a><span data-ttu-id="251ec-104">生成 Contoso 和 Fabrikam 加密证书</span><span class="sxs-lookup"><span data-stu-id="251ec-104">To generate the Contoso and Fabrikam encryption certificates</span></span>  

1. <span data-ttu-id="251ec-105">在用作证书颁发机构的计算机上，在 Internet Explorer 中找到并打开 http://<contoso 计算机名称>/certsrv。</span><span class="sxs-lookup"><span data-stu-id="251ec-105">On the computer you used as the Certification Authority, in Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  

2. <span data-ttu-id="251ec-106">上**欢迎**页上，单击**申请一个证书**。</span><span class="sxs-lookup"><span data-stu-id="251ec-106">On the **Welcome** page, click **Request a certificate**.</span></span>  

3. <span data-ttu-id="251ec-107">上**申请一个证书**页上，单击**高级的证书申请**。</span><span class="sxs-lookup"><span data-stu-id="251ec-107">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  

4. <span data-ttu-id="251ec-108">上**高级证书申请**页上，单击**创建并向此 CA 提交一个申请**。</span><span class="sxs-lookup"><span data-stu-id="251ec-108">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  

5. <span data-ttu-id="251ec-109">上**高级证书申请**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="251ec-109">On the **Advanced Certificate Request** page, do the following:</span></span>  


   |            <span data-ttu-id="251ec-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="251ec-110">Use this</span></span>            |                                                                         <span data-ttu-id="251ec-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="251ec-111">To do this</span></span>                                                                         |
   |--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            <span data-ttu-id="251ec-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="251ec-112">**Name**</span></span>            |                                                               <span data-ttu-id="251ec-113">类型**Fabrikam 加密**。</span><span class="sxs-lookup"><span data-stu-id="251ec-113">Type **Fabrikam Encryption**.</span></span>                                                                |
   |           <span data-ttu-id="251ec-114">**电子邮件**</span><span class="sxs-lookup"><span data-stu-id="251ec-114">**E-Mail**</span></span>           |                                                          <span data-ttu-id="251ec-115">类型<strong>jdoe@fabrikam.com</strong>。</span><span class="sxs-lookup"><span data-stu-id="251ec-115">Type <strong>jdoe@fabrikam.com</strong>.</span></span>                                                          |
   |          <span data-ttu-id="251ec-116">**Company**</span><span class="sxs-lookup"><span data-stu-id="251ec-116">**Company**</span></span>           |                                                                     <span data-ttu-id="251ec-117">类型**Fabrikam**。</span><span class="sxs-lookup"><span data-stu-id="251ec-117">Type **Fabrikam**.</span></span>                                                                     |
   |         <span data-ttu-id="251ec-118">**部门**</span><span class="sxs-lookup"><span data-stu-id="251ec-118">**Department**</span></span>         |                                                                       <span data-ttu-id="251ec-119">类型**测试**。</span><span class="sxs-lookup"><span data-stu-id="251ec-119">Type **Test**.</span></span>                                                                       |
   |            <span data-ttu-id="251ec-120">**City**</span><span class="sxs-lookup"><span data-stu-id="251ec-120">**City**</span></span>            |                                                                       <span data-ttu-id="251ec-121">类型**测试**。</span><span class="sxs-lookup"><span data-stu-id="251ec-121">Type **Test**.</span></span>                                                                       |
   |           <span data-ttu-id="251ec-122">**State**</span><span class="sxs-lookup"><span data-stu-id="251ec-122">**State**</span></span>            |                                                                       <span data-ttu-id="251ec-123">类型**测试**。</span><span class="sxs-lookup"><span data-stu-id="251ec-123">Type **Test**.</span></span>                                                                       |
   |       <span data-ttu-id="251ec-124">**国家/地区**</span><span class="sxs-lookup"><span data-stu-id="251ec-124">**Country/Region**</span></span>       |                                                                        <span data-ttu-id="251ec-125">类型**美国**。</span><span class="sxs-lookup"><span data-stu-id="251ec-125">Type **US**.</span></span>                                                                        |
   | <span data-ttu-id="251ec-126">**需要的证书类型**</span><span class="sxs-lookup"><span data-stu-id="251ec-126">**Type of Certificate Needed**</span></span> |                                             <span data-ttu-id="251ec-127">选择**电子邮件保护证书**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="251ec-127">Select **E-Mail Protection Certificate** from the drop down list.</span></span>                                              |
   |         <span data-ttu-id="251ec-128">**密钥用法**</span><span class="sxs-lookup"><span data-stu-id="251ec-128">**Key Usage**</span></span>          |                                                              <span data-ttu-id="251ec-129">选择**Exchange**选项。</span><span class="sxs-lookup"><span data-stu-id="251ec-129">Select the **Exchange** option.</span></span>                                                               |
   |   <span data-ttu-id="251ec-130">**附加密钥选项**</span><span class="sxs-lookup"><span data-stu-id="251ec-130">**Additional Key Options**</span></span>   | <span data-ttu-id="251ec-131">请选中以下选项：</span><span class="sxs-lookup"><span data-stu-id="251ec-131">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="251ec-132">-   **标记密钥为可导出**</span><span class="sxs-lookup"><span data-stu-id="251ec-132">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="251ec-133">-   **将证书保存在本地计算机证书存储**</span><span class="sxs-lookup"><span data-stu-id="251ec-133">-   **Store certificate in the local computer certificate store**</span></span> |
   |       <span data-ttu-id="251ec-134">**友好名称**</span><span class="sxs-lookup"><span data-stu-id="251ec-134">**Friendly Name**</span></span>        |                                                               <span data-ttu-id="251ec-135">类型**Fabrikam 加密**。</span><span class="sxs-lookup"><span data-stu-id="251ec-135">Type **Fabrikam Encryption**.</span></span>                                                                |


6. <span data-ttu-id="251ec-136">单击**提交**，然后单击**是**中**Web 访问确认**对话框。</span><span class="sxs-lookup"><span data-stu-id="251ec-136">Click **Submit**, and then click **Yes** in **Web Access Confirmation** dialog box.</span></span>  

7. <span data-ttu-id="251ec-137">上**证书颁发**页上，单击**安装此证书**。</span><span class="sxs-lookup"><span data-stu-id="251ec-137">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  

8. <span data-ttu-id="251ec-138">重复步骤 1-7，更改中的信息**名称**框中**识别信息**部分并**好记的名称**框**Contoso加密**。</span><span class="sxs-lookup"><span data-stu-id="251ec-138">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Encryption**.</span></span>  

### <a name="to-generate-the-contoso-and-fabrikam-signing-certificates"></a><span data-ttu-id="251ec-139">生成 Contoso 和 Fabrikam 签名证书</span><span class="sxs-lookup"><span data-stu-id="251ec-139">To generate the Contoso and Fabrikam Signing Certificates</span></span>  

1. <span data-ttu-id="251ec-140">在 Internet Explorer 中，找到并打开 http://<contoso 计算机名称>/certsrv。</span><span class="sxs-lookup"><span data-stu-id="251ec-140">In Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  

2. <span data-ttu-id="251ec-141">上**欢迎**页上，单击**申请一个证书**。</span><span class="sxs-lookup"><span data-stu-id="251ec-141">On the **Welcome** page, click **Request a certificate**.</span></span>  

3. <span data-ttu-id="251ec-142">上**申请一个证书**页上，单击**高级的证书申请**。</span><span class="sxs-lookup"><span data-stu-id="251ec-142">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  

4. <span data-ttu-id="251ec-143">上**高级证书申请**页上，单击**创建并向此 CA 提交一个申请**。</span><span class="sxs-lookup"><span data-stu-id="251ec-143">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  

5. <span data-ttu-id="251ec-144">上**高级证书申请**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="251ec-144">On the **Advanced Certificate Request** page, do the following:</span></span>  


   |            <span data-ttu-id="251ec-145">使用此选项</span><span class="sxs-lookup"><span data-stu-id="251ec-145">Use this</span></span>            |                                                                         <span data-ttu-id="251ec-146">执行的操作</span><span class="sxs-lookup"><span data-stu-id="251ec-146">To do this</span></span>                                                                         |
   |--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            <span data-ttu-id="251ec-147">**名称**</span><span class="sxs-lookup"><span data-stu-id="251ec-147">**Name**</span></span>            |                                                                <span data-ttu-id="251ec-148">类型**Fabrikam 签名**。</span><span class="sxs-lookup"><span data-stu-id="251ec-148">Type **Fabrikam Signature**.</span></span>                                                                |
   |           <span data-ttu-id="251ec-149">**电子邮件**</span><span class="sxs-lookup"><span data-stu-id="251ec-149">**E-Mail**</span></span>           |                                                          <span data-ttu-id="251ec-150">类型<strong>jdoe@fabrikam.com</strong>。</span><span class="sxs-lookup"><span data-stu-id="251ec-150">Type <strong>jdoe@fabrikam.com</strong>.</span></span>                                                          |
   |          <span data-ttu-id="251ec-151">**Company**</span><span class="sxs-lookup"><span data-stu-id="251ec-151">**Company**</span></span>           |                                                                     <span data-ttu-id="251ec-152">类型**Fabrikam**。</span><span class="sxs-lookup"><span data-stu-id="251ec-152">Type **Fabrikam**.</span></span>                                                                     |
   |         <span data-ttu-id="251ec-153">**部门**</span><span class="sxs-lookup"><span data-stu-id="251ec-153">**Department**</span></span>         |                                                                       <span data-ttu-id="251ec-154">类型**测试**。</span><span class="sxs-lookup"><span data-stu-id="251ec-154">Type **Test**.</span></span>                                                                       |
   |            <span data-ttu-id="251ec-155">**City**</span><span class="sxs-lookup"><span data-stu-id="251ec-155">**City**</span></span>            |                                                                       <span data-ttu-id="251ec-156">类型**测试**。</span><span class="sxs-lookup"><span data-stu-id="251ec-156">Type **Test**.</span></span>                                                                       |
   |           <span data-ttu-id="251ec-157">**State**</span><span class="sxs-lookup"><span data-stu-id="251ec-157">**State**</span></span>            |                                                                       <span data-ttu-id="251ec-158">类型**测试**。</span><span class="sxs-lookup"><span data-stu-id="251ec-158">Type **Test**.</span></span>                                                                       |
   |       <span data-ttu-id="251ec-159">**国家/地区**</span><span class="sxs-lookup"><span data-stu-id="251ec-159">**Country/Region**</span></span>       |                                                                        <span data-ttu-id="251ec-160">类型**美国**。</span><span class="sxs-lookup"><span data-stu-id="251ec-160">Type **US**.</span></span>                                                                        |
   | <span data-ttu-id="251ec-161">**需要的证书类型**</span><span class="sxs-lookup"><span data-stu-id="251ec-161">**Type of Certificate Needed**</span></span> |                                             <span data-ttu-id="251ec-162">选择**电子邮件保护证书**从此下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="251ec-162">Select **E-Mail Protection Certificate**.from the drop down list.</span></span>                                              |
   |         <span data-ttu-id="251ec-163">**密钥用法**</span><span class="sxs-lookup"><span data-stu-id="251ec-163">**Key Usage**</span></span>          |                                                              <span data-ttu-id="251ec-164">选择**签名**选项。</span><span class="sxs-lookup"><span data-stu-id="251ec-164">Select the **Signature** option.</span></span>                                                              |
   |   <span data-ttu-id="251ec-165">**附加密钥选项**</span><span class="sxs-lookup"><span data-stu-id="251ec-165">**Additional Key Options**</span></span>   | <span data-ttu-id="251ec-166">请选中以下选项：</span><span class="sxs-lookup"><span data-stu-id="251ec-166">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="251ec-167">-   **标记密钥为可导出**</span><span class="sxs-lookup"><span data-stu-id="251ec-167">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="251ec-168">-   **将证书保存在本地计算机证书存储**</span><span class="sxs-lookup"><span data-stu-id="251ec-168">-   **Store certificate in the local computer certificate store**</span></span> |
   |       <span data-ttu-id="251ec-169">**友好名称**</span><span class="sxs-lookup"><span data-stu-id="251ec-169">**Friendly Name**</span></span>        |                                                                <span data-ttu-id="251ec-170">类型**Fabrikam 签名**。</span><span class="sxs-lookup"><span data-stu-id="251ec-170">Type **Fabrikam Signature**.</span></span>                                                                |


6. <span data-ttu-id="251ec-171">单击**提交**，然后单击**是**要求申请证书时。</span><span class="sxs-lookup"><span data-stu-id="251ec-171">Click **Submit**, and then click **Yes** when asked to request the certificate.</span></span>  

7. <span data-ttu-id="251ec-172">上**证书颁发**页上，单击**安装此证书**。</span><span class="sxs-lookup"><span data-stu-id="251ec-172">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  

8. <span data-ttu-id="251ec-173">重复步骤 1-7，更改中的信息**名称**框中**识别信息**部分并**好记的名称**框**Contoso签名**。</span><span class="sxs-lookup"><span data-stu-id="251ec-173">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Signature**.</span></span>  

### <a name="to-generate-private-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="251ec-174">生成用作加密证书和签名证书的私用证书</span><span class="sxs-lookup"><span data-stu-id="251ec-174">To generate private certificates for the Encryption and Signature certificates</span></span>  

1.  <span data-ttu-id="251ec-175">单击**启动**，单击**运行**，类型**MMC**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="251ec-175">Click **Start**, click **Run**, type **MMC**, and then click **OK**.</span></span>  

2.  <span data-ttu-id="251ec-176">在 console1 窗口中，在**文件**菜单上，单击**添加/删除管理单元中**。</span><span class="sxs-lookup"><span data-stu-id="251ec-176">In the Console1 window, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  

3.  <span data-ttu-id="251ec-177">在添加/删除管理单元对话框中，在**独立**选项卡上，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="251ec-177">In the Add/Remove Snap-in dialog box, on the **Standalone** tab, click **Add**.</span></span>  

4.  <span data-ttu-id="251ec-178">在添加独立管理单元对话框中，选择**证书**中管理单元**可用的独立管理单元**列表，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="251ec-178">In the Add Standalone Snap-in dialog box, select the **Certificates** snap-in from the **Available Standalone Snap-ins** list, and then click **Add**.</span></span>  

5.  <span data-ttu-id="251ec-179">在证书管理单元对话框中，选择**我的用户帐户**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="251ec-179">In the Certificates snap-in dialog box, select **My user account**, and then click **Next**.</span></span>  

6.  <span data-ttu-id="251ec-180">在选择计算机对话框中，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="251ec-180">In the Select Computer dialog box, click **Finish**.</span></span>  

7.  <span data-ttu-id="251ec-181">在添加独立管理单元对话框中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="251ec-181">In the Add Standalone Snap-in dialog box, click **Close**.</span></span>  

8.  <span data-ttu-id="251ec-182">在添加/删除管理单元对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="251ec-182">In the Add/Remove Snap-in dialog box, click **OK**.</span></span>  

9. <span data-ttu-id="251ec-183">在 console1 窗口中，展开**证书 （本地计算机）**，展开**个人**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="251ec-183">In the Console1 window, expand **Certificates (Local Computer)**, expand **Personal**, and then click **Certificates**.</span></span>  

10. <span data-ttu-id="251ec-184">在右窗格中，右键单击**Fabrikam 加密**证书，依次指向**的所有任务**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="251ec-184">In the right pane, right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  

11. <span data-ttu-id="251ec-185">上**欢迎使用证书导出向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="251ec-185">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  

12. <span data-ttu-id="251ec-186">上**导出私钥**页上，选择**是，导出私钥**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="251ec-186">On the **Export Private Key** page, select **Yes, export the private key**, and then click **Next**.</span></span>  

13. <span data-ttu-id="251ec-187">上**导出文件格式**页上，请确保**个人信息交换**是唯一的选项选择，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="251ec-187">On the **Export File Format** page, make sure that **Personal Information Exchange** is the only option selected, and then click **Next**.</span></span>  

14. <span data-ttu-id="251ec-188">上**密码**页上，在**密码**并**确认密码**框中，键入**mysecret**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="251ec-188">On the **Password** page, in the **Password** and **Confirm Password** boxes, type **mysecret**, and then click **Next**.</span></span>  

15. <span data-ttu-id="251ec-189">上**文件导出**页上，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="251ec-189">On the **File To Export** page, click **Browse**.</span></span>  

16. <span data-ttu-id="251ec-190">在中**另存为**对话框中，将证书使用的文件路径保存*\<驱动器\>*: \Certs\Fabrikam Private Encryption.pfx。</span><span class="sxs-lookup"><span data-stu-id="251ec-190">In the **Save As** dialog box, save the certificate using the file path *\<drive\>*:\Certs\Fabrikam Private Encryption.pfx.</span></span>  

17. <span data-ttu-id="251ec-191">上**导出的文件**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="251ec-191">On the **File to Export** page, click **Next**.</span></span>  

18. <span data-ttu-id="251ec-192">上**正在完成证书导出向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="251ec-192">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  

19. <span data-ttu-id="251ec-193">在指示导出成功证书导出向导弹出窗口中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="251ec-193">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  

20. <span data-ttu-id="251ec-194">对于“Fabrikam 签名”证书，请重复步骤 10 到步骤 19，并使用 Fabrikam Private Signature.pfx 文件名。</span><span class="sxs-lookup"><span data-stu-id="251ec-194">Repeat steps 10-19 for the Fabrikam Signature certificate using the file name Fabrikam Private Signature.pfx.</span></span>  

21. <span data-ttu-id="251ec-195">对于“Contoso 签名”证书和“Contoso 加密”证书，请分别重复步骤 10 到步骤 19，并分别使用 Contoso Private Signature.pfx 和 Contoso Private Encryption.pfx 文件名。</span><span class="sxs-lookup"><span data-stu-id="251ec-195">Repeat steps 10-19 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Private Signature.pfx and Contoso Private Encryption.pfx, respectively.</span></span>  

### <a name="to-generate-public-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="251ec-196">生成用作加密证书和签名证书的公用证书</span><span class="sxs-lookup"><span data-stu-id="251ec-196">To generate public certificates for the Encryption and Signature certificates</span></span>  

1.  <span data-ttu-id="251ec-197">在 console1 窗口中，展开**证书-当前用户**，展开**个人**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="251ec-197">In the Console1 window, expand **Certificates – Current User**, expand **Personal**, and then click **Certificates**.</span></span>  

2.  <span data-ttu-id="251ec-198">右键单击**Fabrikam 加密**证书，依次指向**的所有任务**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="251ec-198">Right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  

3.  <span data-ttu-id="251ec-199">上**欢迎使用证书导出向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="251ec-199">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  

4.  <span data-ttu-id="251ec-200">上**导出私钥**页上，选择**否，不导出私钥**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="251ec-200">On the **Export Private Key** page, select **No, do not export the private key**, and then click **Next**.</span></span>  

5.  <span data-ttu-id="251ec-201">上**导出文件格式**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="251ec-201">On the **Export File Format** page, click **Next**.</span></span>  

6.  <span data-ttu-id="251ec-202">上**文件导出**页上，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="251ec-202">On the **File To Export** page, click **Browse**.</span></span>  

7.  <span data-ttu-id="251ec-203">在另存为对话框中，输入**\<驱动器\>: \Certs**有关**中保存**， **Fabrikam Public Encryption.cer**作为**文件名称**，并 **\*.cer**有关**另存为类型**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="251ec-203">In the Save As dialog box, enter **\<drive\>:\Certs** for **Save in**, **Fabrikam Public Encryption.cer** as **File name**, and **\*.cer** for **Save as type**, and then click **Save**.</span></span>  

8.  <span data-ttu-id="251ec-204">上**导出的文件**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="251ec-204">On the **File to Export** page, click **Next**.</span></span>  

9. <span data-ttu-id="251ec-205">上**正在完成证书导出向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="251ec-205">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  

10. <span data-ttu-id="251ec-206">在指示导出成功证书导出向导弹出窗口中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="251ec-206">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  

11. <span data-ttu-id="251ec-207">对于“Fabrikam 签名”证书，请重复步骤 1 到步骤 9，并使用 Fabrikam Public Signature.cer 文件名。</span><span class="sxs-lookup"><span data-stu-id="251ec-207">Repeat steps 1-9 for the Fabrikam Signature certificate using the file name Fabrikam Public Signature.cer.</span></span>  

12. <span data-ttu-id="251ec-208">对于“Contoso 签名”证书和“Contoso 加密”证书，请分别重复步骤 1 到步骤 9，并分别使用 Contoso Public Signature.cer 和 Contoso Public Encryption.cer 文件名。</span><span class="sxs-lookup"><span data-stu-id="251ec-208">Repeat steps 1-9 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Public Signature.cer and Contoso Public Encryption.cer, respectively.</span></span>  

## <a name="see-also"></a><span data-ttu-id="251ec-209">请参阅</span><span class="sxs-lookup"><span data-stu-id="251ec-209">See Also</span></span>  
 [<span data-ttu-id="251ec-210">步骤 3：导入公共和私有证书</span><span class="sxs-lookup"><span data-stu-id="251ec-210">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)