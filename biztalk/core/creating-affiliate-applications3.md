---
title: 创建 Affiliate Applications3 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- affiliate applications
- Single Sign-On, creating tickets
- tickets, creating Single Sign-On
- affiliate applications, creating
- SSO tickets
ms.assetid: 800644fd-2286-4e59-894b-260f584dd29f
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 857ee7edd623332e72176ac09082f0ec9fc460f4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="creating-affiliate-applications"></a>创建关联应用程序
下列步骤介绍了如何开始使用关联应用程序和单一登录 (SSO)。  
  
> [!NOTE]
>  如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户，因为它会影响 ESSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
## <a name="creating-an-affiliate-application"></a>创建关联应用程序  
  
#### <a name="to-create-an-affiliate-application"></a>若要创建关联应用程序  
  
1.  在 **控制面板**, ，打开 **服务**, ，并验证企业单一登录服务正在运行。  
  
2.  在命令提示符下，将目录更改为 Enterprise Single Sign-On 文件夹。  
  
     例如：  
  
     **C:\Program Files\Common Files\Enterprise 上单一登录 >**  
  
3.  使用企业单一登录命令。 有关命令列表，请使用 -help 开关。  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  若要创建关联应用程序中使用 *。XML 作为一个开始，键入以下命令︰  
  
     **ssomanage.exe createapps C:\SSOtest\AffiliateApplication.xml**  
  
     其中：  
  
     C:\SSOtest 是包含你的应用程序 XML 的文件夹。  
  
     AffiliateApplication.xml 是应用程序创建包含登录信息的 XML。  
  
     例如：  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
         <application name="JDEdwardsApp">  
              <description>JDEdwards SSO Application</description>  
              <contact>someone@microsoft.com</contact>  
              <userGroup>ibi\Domain Users</userGroup>  
              <!—-an existing group on the domain controller - >   
              <appAdminGroup>ibi\YourID</appAdminGroup>  
              <!-- an existing account within the domain group - >   
              <field ordinal="0" label="User ID" masked="no" />  
              <field ordinal="1" label="Password" masked="yes" />  
              <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
         </application>  
    </SSO>  
    ```  
  
## <a name="creating-single-sign-on-tickets"></a>创建单一登录票证  
  
#### <a name="to-create-sso-tickets"></a>创建 SSO 票证  
  
1.  键入以下命令来控制 SSO 票证行为：  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  回答以下问题：  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完成后，您将收到以下确认：  
  
     **使用此计算机上的 SSO 服务器。已成功完成该操作。**  
  
## <a name="enabling-the-affiliate-application-xml"></a>启用关联应用程序 XML  
  
#### <a name="to-enable-affiliate-application-xml"></a>启用关联应用程序 XML  
  
1.  键入以下命令︰  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  键入以下命令以列出应用程序并验证是否已创建该应用程序：  
  
     `ssoclient.exe –listapps`  
  
     列表中显示 Affiliate 应用程序可供使用。  
  
     **有关 IBI\YourID-JDEdwardsApp 可用应用程序**  
  
3.  键入以下命令，设置关联应用程序的凭据：  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  在提示符下输入用户名和密码。 输入 JDEdwardsApp 关联应用程序的登录凭据。 例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。  
  
    -   **用户 ID:** 用户  
  
    -   **密码︰** ******  
  
    -   **确认？密码︰** ******  
  
5.  此关联应用程序显示在“JD Edwards OneWorld 传输属性”对话框的 BizTalk 适配器的下拉列表中。  
  
## <a name="see-also"></a>另请参阅  
 [适配器中的安全](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)