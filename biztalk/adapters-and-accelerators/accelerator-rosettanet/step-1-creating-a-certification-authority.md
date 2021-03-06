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
# <a name="step-1-creating-a-certification-authority"></a>第 1 步：创建证书颁发机构
在本主题中，安装证书服务[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]组件。 用于生成在你需要升级 Contoso 和 Fabrikam 组织之间进行安全通信的证书。 每个贸易合作伙伴将具有用于通信的专用加密证书和身份标识的专用签名证书。 此外，合作伙伴将共享与其他实现 3A2 合作伙伴接口流程 (PIP) 时升级安全通信的公钥证书。  
  
### <a name="to-install-the-certificate-server"></a>若要安装证书服务器  
  
1.  单击**启动**，依次指向**设置**，然后单击**控制面板**。 双击**添加或删除程序**。  
  
2.  在中**添加或删除程序**对话框中，单击**添加/删除 Windows 组件**。  
  
3.  上**Windows 组件向导**页上，在**组件**部分中，选择**证书服务**，单击**是**，然后单击**下一步**以启动配置组件向导。  
  
    > [!NOTE]
    >  如果**证书服务 Windows**组件已被选定，跳过此过程的其余部分。  
  
4.  上**CA 类型**页上，请确保**独立根 CA**已选择，然后单击**下一步**。  
  
5.  上**CA 标识信息**页上，在**该 CA 的公用名**框中，键入**Contoso-fabrikamca**，然后单击**下一步**。  
  
6.  上**证书数据库设置**页上，保留默认值，，然后单击**下一步**。  
  
7.  单击**是**时向导将提示你停止 Internet 信息服务 (IIS)。  
  
8.  单击**是**如果**配置组件向导**会提示你启用 Active Server Pages。  
  
9. 单击**完成**以关闭**Windows 组件向导**。  
  
    > [!NOTE]
    >  只需一台计算机用作证书颁发机构。 不需要第二台计算机上重复此步骤。 本教程将 Contoso 计算机用作证书颁发机构。  
  
### <a name="to-install-a-root-certification-authority-ca-for-windows-server-2008"></a>若要安装适用于 Windows Server 2008 的根证书颁发机构 (CA)  
  
1.  打开服务器管理器中，单击**添加角色**在角色中，单击**下一步**，然后单击**Active Directory 证书**Services 复选框。 单击**下一步**两次。  
  
2.  在选择角色服务页上，单击**证书颁发机构和证书颁发机构 Web 注册**。 单击“下一步” 。  
  
3.  在指定安装类型页上，单击**独立**。 单击“下一步” 。  
  
4.  在指定 CA 类型页上，单击根 CA。 单击“下一步” 。  
  
5.  在设置私钥页上，单击创建新的私钥。 单击“下一步” 。  
  
6.  在 CA 页配置加密。 单击“下一步” 。  
  
7.  配置 CA 名称，在该框 CA 的公用名中键入 Contoso-fabrikamca，，然后单击**下一步**。  
  
8.  在设置有效期页上，单击**下一步**。  
  
9. 在配置证书数据库页上单击**下一步**。  
  
10. 在确认安装选项页上，单击**安装**。  
  
### <a name="configuring-the-web-site-for-the-ca-to-use-https-authentication"></a>配置 CA 以使用 HTTPS 身份验证网站  
  
1.  在用作证书颁发机构的计算机，单击开始、 指向所有程序、 都指向管理工具，然后单击 Internet 信息服务 (IIS) 管理器。  
  
2.  在 Internet 信息服务 (IIS) 管理器对话框中，右键单击**Default Web Site 和选择编辑绑定...** 从弹出菜单。  
  
3.  在站点绑定对话框中单击**添加**。  
  
4.  在添加网站绑定对话框中选择**https**类型下拉列表中，选择从证书**SSL 证书**下拉列表中，单击**确定**。  
  
5.  单击**关闭**关闭网站绑定... 对话框。  
  
### <a name="to-download-the-ca-certificate"></a>若要下载的 CA 证书  
  
1.  在 Internet Explorer 中，找到并打开 http://<contoso_computername>/certsrv/Default.asp。  
  
2.  在 Default.asp 页上，单击**下载 CA 证书、 证书链或 CRL**。  
  
3.  请确保**当前 [Contoso-fabrikamca]** 中选择**CA 证书**列表，，然后单击**下载 CA 证书**。  
  
4.  将证书保存到 C:\Certs\Contoso-FabrikamCA.cer，Contoso 和 Fabrikam 计算机上。  
  
### <a name="to-import-the-ca-certificate-to-the-trusted-root-certification-authorities-store"></a>CA 证书导入到受信任的根证书颁发机构存储区  
  
1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符处，转到**\<驱动器\>: \Program Files\MicrosoftBizTalk\<版本\>Accelerator for RosettaNet\SDK**，然后按**Enter**.  
  
3.  在命令提示符处，键入**CertWizard /Rootkey"\<驱动器\>: \Certs\Contoso-FabrikamCA.cer"**，然后按**Enter**。  
  
    > [!IMPORTANT]
    >  Contoso 和 Fabrikam 计算机上执行此过程。  
  
### <a name="to-enable-automatic-certificate-issuing"></a>若要启用自动颁发证书  
  
1.  在用作证书颁发机构的计算机，单击**启动**，依次指向**程序**，指向**管理工具**，然后单击**证书颁发机构**。  
  
2.  在证书颁发机构对话框中，右键单击**Contoso-fabrikamca**，然后单击**属性**。  
  
3.  在 Contoso-fabrikamca 属性对话框中，在**策略模块**选项卡上，单击**属性**。  
  
4.  在属性对话框中，选择 **，按照证书模板中的设置**，然后单击**确定**。  
  
5.  单击**确定**以关闭 Contoso-fabrikamca 对话框。  
  
6.  关闭证书颁发机构对话框。  
  
    > [!NOTE]
    >  通过启用自动颁发证书，证书服务会自动将证书颁发过程。 你将需要重新启动证书服务才能应用此更改。  
    >   
    >  您可能需要根证书 Contoso-fabrikamca.cer 安装在 Current User\Trusted Root Certification 颁发机构。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2：创建公用和私用证书](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)