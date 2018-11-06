---
title: 创建关联 Applications4 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets, Single Sign-On
- affiliate applications, setting credentials
- affiliate applications
- Single Sign-On, creating tickets
- SSO tickets
ms.assetid: 790fbe21-8081-4d57-803f-23014c8a3135
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a62a8c2c6d2bb74c9e68fcdcf1304e6d0cd99d67
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752621"
---
# <a name="creating-affiliate-applications"></a>创建关联应用程序
以下步骤介绍如何使用 SSO 开始使用关联应用程序。  
  
> [!NOTE]
>  如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户，因为它会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用。  
  
### <a name="to-create-an-affiliate-application"></a>若要创建关联应用程序  
  
1. 在控制面板中，打开**Services**，并验证是否正在运行企业单一登录服务。  
  
2. 在命令提示符下，将目录更改为 Enterprise Single Sign On 文件夹。  
  
    例如：  
  
    **C:\Program Files\Common Files\Enterprise Single Sign-on >**  
  
3. 使用企业单一登录命令。 命令的列表，请 **-帮助**切换。  
  
4. 若要创建关联应用程序使用\*。XML 作为一个开始，请键入以下命令：  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    其中：  
  
   - C:\SSOtest 是您的应用程序 XML 所在的文件夹。  
  
   - AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。  
  
     例如：  
  
   ```  
   <?xml version="1.0"?>  
   <SSO>  
       <application name="JDEdwardsApp">  
           <description>JDEdwards SSO Application</description>  
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
  
### <a name="to-create-single-sign-on-tickets"></a>创建单一登录票证  
  
1.  键入以下命令以便控制 SSO 票证行为：  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  回答如下所示的问题：  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完成后，你将收到以下确认：  
  
     **在此计算机上使用 SSO 服务器。已成功完成该操作。**  
  
### <a name="to-enable-affiliate-application-xml"></a>启用关联应用程序 XML  
  
1. 键入下列命令：  
  
    `ssomanage -enableapp JDEdwardsApp`  
  
2. 键入以下命令列出应用程序并验证是否已创建应用程序：  
  
    `ssoclient.exe –listapps`  
  
    可用于关联应用程序使用显示在列表中：  
  
    **可用的应用程序用于 IBI\YourID-JDEdwardsApp**  
  
3. 键入以下命令，设置关联应用程序凭据：  
  
    `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4. 在提示符下输入用户名和密码。 输入 JDEdwardsApp 关联应用程序的登录凭据。  
  
    例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。  
  
   - 用户 ID:**用户**  
  
   - 密码： `******`  
  
   - 确认？ 密码： `******`  
  
     关联应用程序将显示在 BizTalk 适配器用于 JD Edwards EnterpriseOne**传输属性**对话框。  
  
## <a name="see-also"></a>请参阅  
 [用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)