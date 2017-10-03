---
title: "创建 Affiliate Applications5 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, affiliate
- Single Sign-On, tickets
- affiliate applications
- creating affiliate applications
- tickets, SSO
- affiliate applications, enabling XML
- SSO tickets
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc6b42a6f3251d9e897af21fcb4207b6790e91cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-affiliate-applications"></a>创建关联应用程序
以下步骤描述如何开始使用关联应用程序和单一登录 (SSO)。  
  
> [!NOTE]
>  如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户；这会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用  
  
### <a name="to-create-an-affiliate-application"></a>若要创建关联应用程序  
  
1.  在 Control Panel 中，打开**服务**，并验证企业单一登录服务正在运行。  
  
2.  在命令提示符下，将目录更改为 Enterprise Single Sign-On 文件夹。  
  
     例如：  
  
     **C:\Program Files\Common Files\Enterprise 上单一登录 >**  
  
3.  使用企业单一登录命令。 有关命令的列表，使用**-帮助**切换。  
  
4.  若要使用 *.XML 作为创建关联应用程序的起始操作，请键入以下命令：  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     其中：  
  
    -   C:\SSOtest 是您的应用程序 XML 所在的文件夹。  
  
    -   AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。  
  
     例如：  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO EMS App">  
            <description>TIBCO EMS SSO Application</description>  
            <contact>someone@example.com</contact>  
            <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
            <!—an existing group on the domain controller - >   
            <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
            <!-- an existing account in the domain group - >   
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
        </application>  
    </SSO>  
    ```  
  
 通过使用示例 XML，关联应用程序（TIBCO EMS App）会包含命令提示符中显示的值。  
  
### <a name="to-create-single-sign-on-tickets"></a>创建单一登录票证  
  
1.  键入以下命令以便控制 SSO 票证行为：  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  回答以下问题：  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完成时，你将收到一条确认消息：  
  
     **使用此计算机上的 SSO 服务器。已成功完成该操作。**  
  
### <a name="to-enable-affiliate-application-xml"></a>启用关联应用程序 XML  
  
1.  键入下列命令：  
  
     `ssomanage -enableapp TIBCO EMSApp`  
  
2.  键入以下命令列出应用程序并验证是否已创建应用程序：  
  
     `ssoclient.exe –listapps`  
  
     列表中将显示可供使用的关联应用程序：  
  
     **有关 IBI\YourID-TIBCO EMSApp 可用应用程序**  
  
3.  键入以下命令以设置应用程序凭据的关联：  
  
     `soclient.exe -setcredentials TIBCO EMSApp`  
  
4.  在提示符下输入用户名和密码。 输入 TIBCO EMS App 关联应用程序的登录凭据。  
  
     例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。  
  
    -   用户 ID:**用户**  
  
    -   密码：`******`  
  
    -   确认？ 密码：`******`  
  
     关联应用程序中的 BizTalk Adapter 显示个 TIBCO EMS**传输属性**对话框。  
  
## <a name="see-also"></a>另请参阅  
 [使用单一登录](../core/using-single-sign-on4.md)