---
title: 使用 BizTalk Server 中证书的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab58264b-2475-4831-9f08-bfbaa293022f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5291327cfe037a38283a984015c0027b7fdc7c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969062"
---
# <a name="known-issues-with-certificates-in-biztalk-server"></a><span data-ttu-id="59776-102">BizTalk Server 中证书的已知的问题</span><span class="sxs-lookup"><span data-stu-id="59776-102">Known Issues with Certificates in BizTalk Server</span></span>
<span data-ttu-id="59776-103">本部分介绍管理与一起使用的数字证书的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="59776-103">This section describes known issues with managing digital certificates used with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="general-certificate-issues"></a><span data-ttu-id="59776-104">常规证书问题</span><span class="sxs-lookup"><span data-stu-id="59776-104">General Certificate Issues</span></span>  
  
### <a name="lack-of-connectivity-to-the-certificate-revocation-list-will-cause-a-certificate-to-be-rejected"></a><span data-ttu-id="59776-105">缺乏与证书吊销列表连接将导致证书被拒绝</span><span class="sxs-lookup"><span data-stu-id="59776-105">Lack of connectivity to the certificate revocation list will cause a certificate to be rejected</span></span>  
 <span data-ttu-id="59776-106">此问题涉及到以下错误:"出现身份验证错误。</span><span class="sxs-lookup"><span data-stu-id="59776-106">This issue involves the following error: “There was an authentication error.</span></span> <span data-ttu-id="59776-107">颁发用于对消息进行签名的证书的证书颁发机构 (CA) 的状态是未知的。"</span><span class="sxs-lookup"><span data-stu-id="59776-107">The status of the certification authority (CA) that issued the certificate used to sign the message is unknown."</span></span> <span data-ttu-id="59776-108">甚至当签名证书无效，在 MMC 中查看时可能发生此错误 (使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用户) 上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="59776-108">This error can occur even when the signing certificate is valid when viewed under MMC (using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] user) on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="59776-109">如果在接收管道中的 S/MIME 解码器组件上启用了"检查证书吊销"属性，则可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="59776-109">This condition can occur if the "Check Certificate Revocation" property is enabled on the S/MIME decoder component in the receive pipeline.</span></span> <span data-ttu-id="59776-110">当此属性设置为 true，BizTalk Server 将尝试查询证书吊销列表 (CRL) 以查看传入的证书已被吊销。</span><span class="sxs-lookup"><span data-stu-id="59776-110">When this property is set to true, BizTalk Server will try to query the Certificate Revocation List (CRL) to see if the incoming certificate has been revoked.</span></span> <span data-ttu-id="59776-111">如果未吊销证书本身并不重要。</span><span class="sxs-lookup"><span data-stu-id="59776-111">It does not matter if the certificate itself is not revoked.</span></span> <span data-ttu-id="59776-112">如果 BizTalk Server 无法查询相应的 CRL，由于连接问题，它将不接受该证书。</span><span class="sxs-lookup"><span data-stu-id="59776-112">If BizTalk Server cannot query the corresponding CRL because of connectivity issues, it will not accept the certificate.</span></span> <span data-ttu-id="59776-113">若要解决此错误，请双击你使用的证书显示证书的属性。</span><span class="sxs-lookup"><span data-stu-id="59776-113">To troubleshoot this error, display the certificate's properties by double-clicking the certificate that you used.</span></span> <span data-ttu-id="59776-114">在其详细信息选项卡上，你将看到字段列表中的属性"CRL 分发点"。</span><span class="sxs-lookup"><span data-stu-id="59776-114">In its Details tab, you will see the attribute "CRL Distribution Point" in the field list.</span></span> <span data-ttu-id="59776-115">应指向 CA 服务器上的 CRL 的此属性中的多个 Url。</span><span class="sxs-lookup"><span data-stu-id="59776-115">There should be several URLs in this attribute that point to the CRL on your CA server.</span></span> <span data-ttu-id="59776-116">在 BizTalk server 必须能够访问任何这些 Url，以检索 CRL。</span><span class="sxs-lookup"><span data-stu-id="59776-116">The BizTalk server must be able to access any of these URLs to retrieve the CRL.</span></span> <span data-ttu-id="59776-117">否则为吊销检查将失败，并且会发出上面的错误。</span><span class="sxs-lookup"><span data-stu-id="59776-117">Otherwise, the revocation checking will fail and the above error will be posted.</span></span>  
  
### <a name="the-other-people-certificate-store-is-not-initialized-until-accessed"></a><span data-ttu-id="59776-118">直到访问未初始化的其他人证书存储区</span><span class="sxs-lookup"><span data-stu-id="59776-118">The Other People Certificate store is not initialized until accessed</span></span>  
 <span data-ttu-id="59776-119">此问题涉及到以下证书存储区错误，当您尝试添加或修改发送/接收端口/位置使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]远程管理员控制台:"无法打开证书存储区"。</span><span class="sxs-lookup"><span data-stu-id="59776-119">This issue involves the following certificate store error when you try to add or modify send/receive ports/locations using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrator console remotely: “Could not open certificate store.”</span></span> <span data-ttu-id="59776-120">和"系统找不到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="59776-120">and “The system cannot find the file specified.</span></span> <span data-ttu-id="59776-121">（系统）"。</span><span class="sxs-lookup"><span data-stu-id="59776-121">(System)”.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59776-122">您可以修改使用管理控制台，如果您直接登录，则这些项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="59776-122">You can modify these artifacts using the administration console if you log on directly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="59776-123">在新安装的计算机上**其他人证书**初始化不存储，除非您一次访问它。</span><span class="sxs-lookup"><span data-stu-id="59776-123">On a newly installed computer, the **Other People Certificate** store is not initialized unless you access it once.</span></span> <span data-ttu-id="59776-124">组在配置期间，可以初始化此**其他人证书**存储，并因此配置已完成哪些组的计算机上未看到此错误。</span><span class="sxs-lookup"><span data-stu-id="59776-124">During the group configuration, you can initialize this **Other People Certificate** store, and as a result not see this error on a computer on which group configuration has been done.</span></span>  
  
### <a name="biztalk-server-only-supports-one-personal-certificate-for-each-biztalk-group"></a><span data-ttu-id="59776-125">BizTalk Server 仅支持一个个人证书用于每个 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="59776-125">BizTalk Server only supports one personal certificate for each BizTalk group</span></span>  
 <span data-ttu-id="59776-126">BizTalk 组使用的个人证书被指定的 BizTalk 组属性中设置的个人证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="59776-126">The personal certificate that is used by the BizTalk group is specified by setting the thumbprint of the personal certificate in the BizTalk group properties.</span></span> <span data-ttu-id="59776-127">BizTalk 组可以表示企业、 部门、 中心或其他业务部门。</span><span class="sxs-lookup"><span data-stu-id="59776-127">A BizTalk group can represent an enterprise, a department, a hub, or another business unit.</span></span>  
  
## <a name="as2-certificate-issues"></a><span data-ttu-id="59776-128">AS2 证书问题</span><span class="sxs-lookup"><span data-stu-id="59776-128">AS2 Certificate Issues</span></span>  
  
### <a name="the-as2-decoder-will-not-validate-that-a-certificate-is-configured-on-the-host-or-for-the-destination-party"></a><span data-ttu-id="59776-129">AS2 解码器将不验证在该主机或目标参与方配置了证书</span><span class="sxs-lookup"><span data-stu-id="59776-129">The AS2 decoder will not validate that a certificate is configured on the host or for the destination party</span></span>  
 <span data-ttu-id="59776-130">只要在证书存储区中配置了消息的私用证书，AS2 解码器就会解密该消息。</span><span class="sxs-lookup"><span data-stu-id="59776-130">The AS2 decoder will decrypt a message as long as the private certificate for that message is configured in the certificate store.</span></span> <span data-ttu-id="59776-131">但是，AS2 解码器将不验证解密证书是否与在主机上配置的证书相同。</span><span class="sxs-lookup"><span data-stu-id="59776-131">However, the AS2 decoder will not validate that the decryption certificate is the same as the certificate configured on the host.</span></span> <span data-ttu-id="59776-132">接收到的消息可使用多个证书进行加密。</span><span class="sxs-lookup"><span data-stu-id="59776-132">The received message can be encrypted with more than one certificate.</span></span>  
  
### <a name="biztalk-server-will-be-unable-to-decrypt-a-message-saved-in-wire-format-if-the-certificate-is-not-valid"></a><span data-ttu-id="59776-133">BizTalk Server 将无法解密以传输格式保存，如果证书不是有效的消息</span><span class="sxs-lookup"><span data-stu-id="59776-133">BizTalk Server will be unable to decrypt a message saved in wire format if the certificate is not valid</span></span>  
 <span data-ttu-id="59776-134">**症状**</span><span class="sxs-lookup"><span data-stu-id="59776-134">**Symptom**</span></span>  
  
 <span data-ttu-id="59776-135">BizTalk Server 无法对不可否认数据库中以传输格式保存的入站 AS2 消息解密。</span><span class="sxs-lookup"><span data-stu-id="59776-135">BizTalk Server is unable to decrypt an inbound AS2 message that was saved in wire format in the non-repudiation database.</span></span>  
  
 <span data-ttu-id="59776-136">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="59776-136">**Possible Cause**</span></span>  
  
 <span data-ttu-id="59776-137">解密消息所需的证书已过期或已被吊销。</span><span class="sxs-lookup"><span data-stu-id="59776-137">The certificate required to decrypt the message has expired or been revoked.</span></span> <span data-ttu-id="59776-138">如果自 AS2 消息保存在不可否认数据库以来已过去一定时间，则更有可能发生上述情况。</span><span class="sxs-lookup"><span data-stu-id="59776-138">This is more likely to occur if a certain period of time has elapsed since the AS2 message was saved in the non-repudiation database.</span></span> <span data-ttu-id="59776-139">如果发生这种情况，则您可能不能立即访问该消息的有效证书。</span><span class="sxs-lookup"><span data-stu-id="59776-139">If this occurs, you may not have immediate access to a valid certificate for the message.</span></span>  
  
 <span data-ttu-id="59776-140">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="59776-140">**Resolution**</span></span>  
  
 <span data-ttu-id="59776-141">获取有效证书，以对消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="59776-141">Acquire a valid certificate for decrypting the message.</span></span>  
  
### <a name="if-an-as2-message-cannot-be-decrypted-the-problem-may-be-fixed-by-re-importing-the-certificate"></a><span data-ttu-id="59776-142">如果不能解密 AS2 消息，可能会通过重新导入的证书来解决问题</span><span class="sxs-lookup"><span data-stu-id="59776-142">If an AS2 message cannot be decrypted, the problem may be fixed by re-importing the certificate</span></span>  
 <span data-ttu-id="59776-143">**症状**</span><span class="sxs-lookup"><span data-stu-id="59776-143">**Symptom**</span></span>  
  
 <span data-ttu-id="59776-144">AS2 解码器在遇到异常时它会尝试解密 AS2 消息，引发以下错误：</span><span class="sxs-lookup"><span data-stu-id="59776-144">The AS2 Decoder encounters an exception when it attempts to decrypt an AS2 message, throwing the following error:</span></span>  
  
```  
"The AS2 Decoder encountered an exception during processing. Details of the message and exception are as follows:   
   AS2-From:"PARTNER" AS2-To:"HOME" MessageID:"<137706.1178060412333@servername>"   
   MessageType: "unknown" Exception:"An error occurred when decrypting an AS2 message."  
System.ArgumentNullException: Value cannot be null.  
Parameter name: PayloadContentType  
at Microsoft.BizTalk.Edi.Reporting.Common.Utilities.ValidateArgument(Object o,  
String parameterName, Boolean isEmptyStringValidationRequired)  
at Microsoft.BizTalk.EdiInt.Reporting.AS2MessageActivity.ValidateParameters()  
at Microsoft.BizTalk.EdiInt.Reporting.AS2MessageActivity.Create()"  
  
```  
  
 <span data-ttu-id="59776-145">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="59776-145">**Possible Cause**</span></span>  
  
 <span data-ttu-id="59776-146">用于解密 AS2 消息的证书需要重新加载到个人存储区中。</span><span class="sxs-lookup"><span data-stu-id="59776-146">The certificate used to decrypt the AS2 message needs to be reloaded into the Personal Store.</span></span>  
  
 <span data-ttu-id="59776-147">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="59776-147">**Resolution**</span></span>  
  
 <span data-ttu-id="59776-148">从个人存储区删除现有的证书，然后使用证书导入向导将证书重新导入到个人存储区。</span><span class="sxs-lookup"><span data-stu-id="59776-148">Delete the existing certificate from the Personal Store, and then re-import the certificate into the Personal Store using the Certificate Import Wizard.</span></span> <span data-ttu-id="59776-149">这样做，请右键单击**证书**下的文件夹**个人存储区**，指向**所有任务**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="59776-149">Do so by right-clicking the **Certificate** folder under the **Personal Store**, pointing to **All Tasks**, and then clicking **Import**.</span></span>  
  
### <a name="use-the-same-logon-for-the-in-process-host-instance-and-the-isolated-host-instance-to-ensure-that-personal-store-is-recognized"></a><span data-ttu-id="59776-150">使用相同的进程内主机实例和独立主机实例的登录名以确保可识别个人存储区</span><span class="sxs-lookup"><span data-stu-id="59776-150">Use the same logon for the in-process host instance and the isolated host instance to ensure that personal store is recognized</span></span>  
 <span data-ttu-id="59776-151">只有在为登录凭据与主机实例关联的用户加载了用户配置文件时，个人证书存储区才可用于消息处理。</span><span class="sxs-lookup"><span data-stu-id="59776-151">The Personal certificate store will be available for message processing only if the user profile is loaded for the user whose logon credentials are associated with the host instance.</span></span> <span data-ttu-id="59776-152">个人存储区用于签名证书和解密证书（用户自己的私钥）。</span><span class="sxs-lookup"><span data-stu-id="59776-152">The Personal store is used for signing and decryption certificates (the user's own private key).</span></span> <span data-ttu-id="59776-153">默认情况下，将为进程内主机实例加载用户配置文件；但默认情况下不会为独立主机实例加载用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="59776-153">The user profile is loaded by default for the in-process host instance; however, the user profile is not loaded by default for the isolated host instance.</span></span> <span data-ttu-id="59776-154">您可以通过应用程序为独立主机加载用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="59776-154">You can have an application load the user profile for the isolated host.</span></span> <span data-ttu-id="59776-155">另外，也可以通过对进程内主机实例和独立主机实例使用相同的登录名来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="59776-155">Alternatively, you can work around this issue by using the same logon for the in-process host instance and the isolated host instance.</span></span>  
  
 <span data-ttu-id="59776-156">您可以创建空服务来加载用户配置文件，而无需让应用程序来加载此文件。</span><span class="sxs-lookup"><span data-stu-id="59776-156">Instead of having an application load the user profile, you can create an empty service to load the profile.</span></span> <span data-ttu-id="59776-157">有关创建空的服务的详细信息，请参阅[如何： 创建 Windows 服务](http://go.microsoft.com/fwlink/?LinkId=155149)(http://go.microsoft.com/fwlink/?LinkId=155149)在 Visual Studio 帮助。</span><span class="sxs-lookup"><span data-stu-id="59776-157">For more information about creating an empty service, see [How to: Create Windows Services](http://go.microsoft.com/fwlink/?LinkId=155149) (http://go.microsoft.com/fwlink/?LinkId=155149) in Visual Studio Help.</span></span>  
  
 <span data-ttu-id="59776-158">创建空服务来加载配置文件之后, 继续执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59776-158">After creating the empty service to load the profile, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="59776-159">单击**启动**，然后单击**运行**以打开**运行**对话框。</span><span class="sxs-lookup"><span data-stu-id="59776-159">Click **Start**, and then click **Run** to open the **Run** dialog box.</span></span>  
  
2.  <span data-ttu-id="59776-160">在**运行**对话框中，键入**service.msc**然后按**ENTER**以打开**服务**mmc 管理单元。</span><span class="sxs-lookup"><span data-stu-id="59776-160">In the **Run** dialog box, type **service.msc** and press **ENTER** to open the **Services** MMC snap-in.</span></span>  
  
3.  <span data-ttu-id="59776-161">打开**属性**对话框中为你创建的服务。</span><span class="sxs-lookup"><span data-stu-id="59776-161">Open the **Properties** dialog box for the service you created.</span></span> <span data-ttu-id="59776-162">右键单击该服务，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="59776-162">Right-click the service and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="59776-163">单击**Log On**选项卡上，选择**此帐户**，然后输入用于独立主机实例的登录名。</span><span class="sxs-lookup"><span data-stu-id="59776-163">Click the **Log On** tab, select **This Account**, and then enter the logon name used for the isolated host instance.</span></span>  
  
5.  <span data-ttu-id="59776-164">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="59776-164">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="59776-165">手动启动服务以加载登录用户的用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="59776-165">Manually start the service to load the user profile for that logon user.</span></span>  
  
### <a name="the-key-usage-attribute-of-a-certificate-must-match-the-certificates-use"></a><span data-ttu-id="59776-166">证书的“密钥用法”属性必须与证书的用途匹配</span><span class="sxs-lookup"><span data-stu-id="59776-166">The Key Usage attribute of a certificate must match the certificate's use</span></span>  
 <span data-ttu-id="59776-167">用于 AS2 传输的证书必须具有实现其用途所需的属性。</span><span class="sxs-lookup"><span data-stu-id="59776-167">Certificates used for AS2 transport must have the attributes required for their intended use.</span></span> <span data-ttu-id="59776-168">对于签名和签名验证，证书的“密钥用法”属性必须为“数字签名”。</span><span class="sxs-lookup"><span data-stu-id="59776-168">For signing and signature verification, the Key Usage attribute of the certificate must be Digital Signature.</span></span> <span data-ttu-id="59776-169">对于加密和解密，证书的“密钥用法”属性必须为“数据加密”或“密钥加密”。</span><span class="sxs-lookup"><span data-stu-id="59776-169">For encryption and decryption, the Key Usage attribute of the certificate must be Data Encipherment or Key Encipherment.</span></span> <span data-ttu-id="59776-170">你可以通过双击证书，单击验证密钥用法属性**详细信息**选项卡**证书**对话框中，并检查**密钥用法**字段.</span><span class="sxs-lookup"><span data-stu-id="59776-170">You can verify the Key Usage attribute by double-clicking the certificate, clicking the **Details** tab in the **Certificate** dialog box, and checking the **Key Usage** field.</span></span>  
  
### <a name="the-certificate-resolution-list-will-be-verified-for-an-outgoing-mdn-if-the-as2-to-property-is-not-set-for-the-party"></a><span data-ttu-id="59776-171">如果没有对参与方设置 AS2-To 属性，则将为传出的 MDN 验证证书解析列表。</span><span class="sxs-lookup"><span data-stu-id="59776-171">The certificate resolution list will be verified for an outgoing MDN if the AS2-To property is not set for the party</span></span>  
 <span data-ttu-id="59776-172">在传出的 MDN 的默认协议中，会执行证书解析列表验证。</span><span class="sxs-lookup"><span data-stu-id="59776-172">In the default agreement for an outgoing MDN, the certificate resolution list verification is performed.</span></span> <span data-ttu-id="59776-173">如果您不希望执行此验证，请确保设置了正确的 AS2-To 参与方属性，以便能够解析接收方并且能够确定参与方属性。</span><span class="sxs-lookup"><span data-stu-id="59776-173">If you do not want this verification to be performed, verify that the correct AS2-To party property is set, so the receiving party can be resolved and the party properties can be determined.</span></span> <span data-ttu-id="59776-174">这样的话，将不使用提示验证证书解析列表的默认协议。</span><span class="sxs-lookup"><span data-stu-id="59776-174">If so, the default agreement that prompts verification of the certificate resolution list will not be used.</span></span> <span data-ttu-id="59776-175">您还将需要在 AS2 参与方属性的“常规”页上禁用“检查证书吊销列表”属性。</span><span class="sxs-lookup"><span data-stu-id="59776-175">You will also need to disable the Check Certification Revocation List property on the General page of the AS2 party properties.</span></span>