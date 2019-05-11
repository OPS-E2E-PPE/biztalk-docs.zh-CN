---
title: 创建关联应用程序用于 TIBCO Rendezvous |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3603fcb-3594-460b-b74a-618e22d9c4e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba94161fa534187392e64e6138b6f8ae18920377
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354024"
---
# <a name="creating-affiliate-applications"></a>创建关联应用程序
以下步骤介绍如何开始使用关联应用程序和单一登录 (SSO)。 有关如何使用企业单一登录的完整信息，请参阅 Microsoft 文档。  
  
> [!NOTE]
>  如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为它会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
## <a name="create-an-affiliate-application"></a>创建关联应用程序  
  
1.  在控制面板中，打开**Services**，并验证是否正在运行企业单一登录服务。  
  
2.  在命令提示符中，将目录更改为 Enterprise Single Sign-on 文件夹。 例如：  
  
     **C:\Program Files\Common Files\Enterprise Single Sign-On>**  
  
3.  使用企业单一登录命令。 命令的列表，请 **-帮助**切换。  
  
4.  若要使用创建的关联应用程序 *。XML 作为一个开始，请键入以下命令：  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     其中：  
  
     C:\SSOtest 是您的应用程序 XML 所在的文件夹。  
  
     AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。  
  
     例如：  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO RendezvousApp">  
            <description> TIBCO Rendezvous SSO Application</description>  
            <contact>someone@microsoft.com</contact>  
            <userGroup>ibi\Domain Users</userGroup>  
            <!—an existing group on the domain controller - >   
            <appAdminGroup>ibi\YourID</appAdminGroup>  
            <!-- an existing account within the domain group - >   
  
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
  
        </application>  
    </SSO>  
    ```  
  
## <a name="create-single-sign-on-tickets"></a>创建单一登录票证  
  
1.  键入以下命令来控制 SSO 票证行为：  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  回答以下问题，如所示：  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
3.  完成后，你将收到以下确认：  
  
     **在此计算机上使用 SSO 服务器。已成功完成该操作。**  
  
## <a name="enable-affiliate-application-xml"></a>启用关联应用程序 XML  
  
1.  键入下列命令：  
  
     `ssomanage -enableapp TIBCO RendezvousApp`  
  
2.  键入以下命令列出应用程序并验证已创建应用程序：  
  
     `ssoclient.exe –listapps`  
  
     在列表中显示可供使用的关联应用程序。  
  
     **可用的应用程序用于 IBI\YourID-TIBCO RendezvousApp**  
  
3.  键入以下命令，设置关联应用程序凭据：  
  
     `ssoclient.exe -setcredentials TIBCO RendezvousApp`  
  
4.  输入用户名和密码在提示进行操作。  
  
5.  输入 TIBCO RendezvousApp 关联应用程序的登录凭据。  
  
     例如，输入用户标识和用户输入到通过 SSO 服务器系统的密码。  
  
    -   用户 ID： 用户  
  
    -   密码: * * *  
  
    -   确认密码: * * *  
  
6.  关联应用程序将显示在 BizTalk 适配器用于 TIBCO Rendezvous**传输属性**对话框。  
  
## <a name="see-also"></a>请参阅  
 [用于 TIBCO Rendezvous 的 BizTalk 适配器的安全性](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)   