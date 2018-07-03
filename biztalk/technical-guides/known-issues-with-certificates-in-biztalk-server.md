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
# <a name="known-issues-with-certificates-in-biztalk-server"></a>BizTalk Server 中证书的已知的问题
本部分介绍管理与一起使用的数字证书的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="general-certificate-issues"></a>常规证书问题  
  
### <a name="lack-of-connectivity-to-the-certificate-revocation-list-will-cause-a-certificate-to-be-rejected"></a>缺乏与证书吊销列表连接将导致证书被拒绝  
 此问题涉及到以下错误:"出现身份验证错误。 颁发用于对消息进行签名的证书的证书颁发机构 (CA) 的状态是未知的。" 甚至当签名证书无效，在 MMC 中查看时可能发生此错误 (使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用户) 上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 如果在接收管道中的 S/MIME 解码器组件上启用了"检查证书吊销"属性，则可能发生这种情况。 当此属性设置为 true，BizTalk Server 将尝试查询证书吊销列表 (CRL) 以查看传入的证书已被吊销。 如果未吊销证书本身并不重要。 如果 BizTalk Server 无法查询相应的 CRL，由于连接问题，它将不接受该证书。 若要解决此错误，请双击你使用的证书显示证书的属性。 在其详细信息选项卡上，你将看到字段列表中的属性"CRL 分发点"。 应指向 CA 服务器上的 CRL 的此属性中的多个 Url。 在 BizTalk server 必须能够访问任何这些 Url，以检索 CRL。 否则为吊销检查将失败，并且会发出上面的错误。  
  
### <a name="the-other-people-certificate-store-is-not-initialized-until-accessed"></a>直到访问未初始化的其他人证书存储区  
 此问题涉及到以下证书存储区错误，当您尝试添加或修改发送/接收端口/位置使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]远程管理员控制台:"无法打开证书存储区"。 和"系统找不到指定的文件。 （系统）"。  
  
> [!NOTE]
>  您可以修改使用管理控制台，如果您直接登录，则这些项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 在新安装的计算机上**其他人证书**初始化不存储，除非您一次访问它。 组在配置期间，可以初始化此**其他人证书**存储，并因此配置已完成哪些组的计算机上未看到此错误。  
  
### <a name="biztalk-server-only-supports-one-personal-certificate-for-each-biztalk-group"></a>BizTalk Server 仅支持一个个人证书用于每个 BizTalk 组  
 BizTalk 组使用的个人证书被指定的 BizTalk 组属性中设置的个人证书的指纹。 BizTalk 组可以表示企业、 部门、 中心或其他业务部门。  
  
## <a name="as2-certificate-issues"></a>AS2 证书问题  
  
### <a name="the-as2-decoder-will-not-validate-that-a-certificate-is-configured-on-the-host-or-for-the-destination-party"></a>AS2 解码器将不验证在该主机或目标参与方配置了证书  
 只要在证书存储区中配置了消息的私用证书，AS2 解码器就会解密该消息。 但是，AS2 解码器将不验证解密证书是否与在主机上配置的证书相同。 接收到的消息可使用多个证书进行加密。  
  
### <a name="biztalk-server-will-be-unable-to-decrypt-a-message-saved-in-wire-format-if-the-certificate-is-not-valid"></a>BizTalk Server 将无法解密以传输格式保存，如果证书不是有效的消息  
 **症状**  
  
 BizTalk Server 无法对不可否认数据库中以传输格式保存的入站 AS2 消息解密。  
  
 **可能的原因**  
  
 解密消息所需的证书已过期或已被吊销。 如果自 AS2 消息保存在不可否认数据库以来已过去一定时间，则更有可能发生上述情况。 如果发生这种情况，则您可能不能立即访问该消息的有效证书。  
  
 **解决方法**  
  
 获取有效证书，以对消息进行解密。  
  
### <a name="if-an-as2-message-cannot-be-decrypted-the-problem-may-be-fixed-by-re-importing-the-certificate"></a>如果不能解密 AS2 消息，可能会通过重新导入的证书来解决问题  
 **症状**  
  
 AS2 解码器在遇到异常时它会尝试解密 AS2 消息，引发以下错误：  
  
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
  
 **可能的原因**  
  
 用于解密 AS2 消息的证书需要重新加载到个人存储区中。  
  
 **解决方法**  
  
 从个人存储区删除现有的证书，然后使用证书导入向导将证书重新导入到个人存储区。 这样做，请右键单击**证书**下的文件夹**个人存储区**，指向**所有任务**，然后单击**导入**。  
  
### <a name="use-the-same-logon-for-the-in-process-host-instance-and-the-isolated-host-instance-to-ensure-that-personal-store-is-recognized"></a>使用相同的进程内主机实例和独立主机实例的登录名以确保可识别个人存储区  
 只有在为登录凭据与主机实例关联的用户加载了用户配置文件时，个人证书存储区才可用于消息处理。 个人存储区用于签名证书和解密证书（用户自己的私钥）。 默认情况下，将为进程内主机实例加载用户配置文件；但默认情况下不会为独立主机实例加载用户配置文件。 您可以通过应用程序为独立主机加载用户配置文件。 另外，也可以通过对进程内主机实例和独立主机实例使用相同的登录名来解决此问题。  
  
 您可以创建空服务来加载用户配置文件，而无需让应用程序来加载此文件。 有关创建空的服务的详细信息，请参阅[如何： 创建 Windows 服务](http://go.microsoft.com/fwlink/?LinkId=155149)(http://go.microsoft.com/fwlink/?LinkId=155149)在 Visual Studio 帮助。  
  
 创建空服务来加载配置文件之后, 继续执行，如下所示：  
  
1.  单击**启动**，然后单击**运行**以打开**运行**对话框。  
  
2.  在**运行**对话框中，键入**service.msc**然后按**ENTER**以打开**服务**mmc 管理单元。  
  
3.  打开**属性**对话框中为你创建的服务。 右键单击该服务，然后选择**属性**。  
  
4.  单击**Log On**选项卡上，选择**此帐户**，然后输入用于独立主机实例的登录名。  
  
5.  单击“确定” 。  
  
6.  手动启动服务以加载登录用户的用户配置文件。  
  
### <a name="the-key-usage-attribute-of-a-certificate-must-match-the-certificates-use"></a>证书的“密钥用法”属性必须与证书的用途匹配  
 用于 AS2 传输的证书必须具有实现其用途所需的属性。 对于签名和签名验证，证书的“密钥用法”属性必须为“数字签名”。 对于加密和解密，证书的“密钥用法”属性必须为“数据加密”或“密钥加密”。 你可以通过双击证书，单击验证密钥用法属性**详细信息**选项卡**证书**对话框中，并检查**密钥用法**字段.  
  
### <a name="the-certificate-resolution-list-will-be-verified-for-an-outgoing-mdn-if-the-as2-to-property-is-not-set-for-the-party"></a>如果没有对参与方设置 AS2-To 属性，则将为传出的 MDN 验证证书解析列表。  
 在传出的 MDN 的默认协议中，会执行证书解析列表验证。 如果您不希望执行此验证，请确保设置了正确的 AS2-To 参与方属性，以便能够解析接收方并且能够确定参与方属性。 这样的话，将不使用提示验证证书解析列表的默认协议。 您还将需要在 AS2 参与方属性的“常规”页上禁用“检查证书吊销列表”属性。