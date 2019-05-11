---
title: 创建关联 Applications3 |Microsoft Docs
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48aaf4d7cd6df05d99f31a9ddce7c6ccb6e7ae68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353950"
---
# <a name="creating-affiliate-applications"></a>创建关联应用程序
以下步骤介绍如何开始使用单一登录 (SSO) 关联应用程序使用。  
  
> [!NOTE]
>  如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为这会影响 ESSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
## <a name="creating-an-affiliate-application"></a>创建关联应用程序  
  
#### <a name="to-create-an-affiliate-application"></a>若要创建关联应用程序  
  
1.  在中**Control Panel**，打开**服务**，并验证是否正在运行企业单一登录服务。  
  
2.  在命令提示符中，将目录更改为 Enterprise Single Sign-on 文件夹。  
  
     例如：  
  
     **C:\Program Files\Common Files\Enterprise Single Sign-On>**  
  
3.  使用企业单一登录命令。 对于命令的列表，请使用-help 开关。  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  若要创建关联应用程序使用 *。XML 作为一个开始，键入以下命令：  
  
     **ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml**  
  
     其中：  
  
     C:\SSOtest 是包含 XML 应用程序的文件夹。  
  
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
  
#### <a name="to-create-sso-tickets"></a>若要创建 SSO 票证  
  
1.  键入以下命令来控制 SSO 票证行为：  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  回答的问题：  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完成后你收到一条确认消息：  
  
     **在此计算机上使用 SSO 服务器。已成功完成该操作。**  
  
## <a name="enabling-the-affiliate-application-xml"></a>启用关联应用程序 XML  
  
#### <a name="to-enable-affiliate-application-xml"></a>若要启用关联应用程序 XML  
  
1.  键入以下命令：  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  键入以下命令以列出的应用程序并验证已创建应用程序中：  
  
     `ssoclient.exe –listapps`  
  
     列表中将显示关联应用程序可供使用。  
  
     **可用的应用程序用于 IBI\YourID-JDEdwardsApp**  
  
3.  键入以下命令，设置关联应用程序凭据：  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  输入用户名和密码在提示进行操作。 输入 JDEdwardsApp 关联应用程序的登录凭据。 例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。  
  
    -   **用户 ID:** 用户  
  
    -   **密码：** ******  
  
    -   **确认？密码：** ******  
  
5.  用于 JD Edwards OneWorld 传输属性对话框中的 BizTalk 适配器的下拉列表中显示的关联应用程序。  
  
## <a name="see-also"></a>请参阅  
 [适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)