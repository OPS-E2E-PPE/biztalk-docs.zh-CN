---
title: 创建用于 TIBCO EMS 的关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914f966f2a5de3acd6daeddbd1912eefc9aa2fb8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966014"
---
# <a name="create-affiliate-applications"></a>创建关联应用程序
以下步骤描述如何开始使用关联应用程序和单一登录 (SSO)。  
  
> [!NOTE]
>  如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户；这会影响企业 SSO 服务的功能。 SSO 仅在域帐户下起作用  
  
## <a name="create-an-affiliate-application"></a>创建关联应用程序  
  
1. 在控制面板中，打开**Services**，并验证是否正在运行企业单一登录服务。  
  
2. 在命令提示符下，将目录更改为 Enterprise Single Sign-On 文件夹。  
  
    例如：  
  
    **C:\Program Files\Common Files\Enterprise Single Sign-on >**  
  
3. 使用企业单一登录命令。 命令的列表，请 **-帮助**切换。  
  
4. 若要使用 *.XML 作为创建关联应用程序的起始操作，请键入以下命令：  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    其中：  
  
   - C:\SSOtest 是您的应用程序 XML 所在的文件夹。  
  
   - AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。  
  
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
  
## <a name="create-single-sign-on-tickets"></a>创建单一登录票证  
  
1.  键入以下命令以便控制 SSO 票证行为：  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  回答以下问题：  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完成后，你将收到一条确认消息：  
  
     **在此计算机上使用 SSO 服务器。已成功完成该操作。**  
  
## <a name="enable-affiliate-application-xml"></a>启用关联应用程序 XML  
  
1. 键入下列命令：  
  
    `ssomanage -enableapp TIBCO EMSApp`  
  
2. 键入以下命令列出应用程序并验证是否已创建应用程序：  
  
    `ssoclient.exe –listapps`  
  
    列表中将显示可供使用的关联应用程序：  
  
    **可用的应用程序用于 IBI\YourID-TIBCO emsapp 的应用程序**  
  
3. 键入以下命令，设置关联应用程序凭据：  
  
    `soclient.exe -setcredentials TIBCO EMSApp`  
  
4. 在提示符下输入用户名和密码。 输入 TIBCO EMS App 关联应用程序的登录凭据。  
  
    例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。  
  
   - 用户 ID:**用户**  
  
   - 密码： `******`  
  
   - 确认？ 密码： `******`  
  
     关联应用程序将显示在 BizTalk 适配器用于 TIBCO EMS**传输属性**对话框。  
  
## <a name="see-also"></a>请参阅  
[保护适配器](../core/security-in-biztalk-adapter-for-tibco-ems.md)