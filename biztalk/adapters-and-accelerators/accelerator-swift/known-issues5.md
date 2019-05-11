---
title: 已知 Issues5 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, known issues
- BizTalk Accelerator for SWIFT, known issues
- known issues
ms.assetid: 0f1ec7dd-9e74-479a-bdc8-ab9c4397c992
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f20477988a3a4f60522a7c05270e72ac525dead
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377310"
---
# <a name="known-issues"></a>已知问题
本部分包含可帮助你避免与 Microsoft 的错误的有用信息[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]。 已知的问题分为以下几个方面：  
  
## <a name="message-repair-and-new-submission"></a>消息修复和新提交

#### <a name="printing-of-a-repair-document-is-recorded-in-the-history-log-even-if-canceled"></a>即使已取消，历史记录日志中记录的修复文档打印  
 如果你运行修复收件箱中的文档打印命令，然后取消打印打印仍然被进入历史记录日志。 发生这种情况是当您打开要在中修复的文档时其[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，单击文件菜单中，打印命令，然后单击打印对话框中的取消。 历史记录日志中的条目，则应将其忽略。  
  
#### <a name="a-duplicate-signature-can-cause-an-xlangs-error-message"></a>重复的签名可能会导致 XLANG/s 错误消息  
 当一个验证程序使用相同的证书作为 repairer[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]挂起消息，并指示不允许重复的签名对错误消息中。 但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]还会生成的事件源为 XLANG/s，该值指示已挂起的 XLANG/s 服务的另一个错误消息。 可以忽略此消息。  
  
#### <a name="message-size-can-affect-repair-performance"></a>消息大小可能会影响修复性能  
 如果你尝试修复非常大的 XML 文件，打开中的 XML 文件时，系统性能会大大降低[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]消息类型的窗体。 内存消耗可能会增加，可能会降低 CPU 占用率，进程可能会因出现错误，指示没有足够的存储可用于完成该操作。  
  
#### <a name="the-last-signature-used-to-sign-a-message-successfully-will-be-authenticated-by-authenticate-signatures"></a>最后一个用于成功对消息进行签名的签名将通过身份验证的签名进行身份验证  
 单击进行身份验证签名按钮[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中只是如果你已登录窗体的阶段验证的签名。 否则，它验证的签名为上一阶段，如果有的话，并将发布以下错误：  
  
 签名用户未正确配置为部门 < department_name > 中 < stage_name > 角色。  
  
 例如，假设您验证阶段后立即处于批准阶段。 如果尚未登录窗体作为审批者，并单击进行身份验证签名[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]验证人使用，不是审批者的签名的签名进行身份验证并发布之前的错误。  

#### <a name="a4swift-cleanup-tool-doesnt-delete-templates"></a>A4SWIFT 清理工具不会删除模板  
 A4SWIFT 清理工具不会执行以下操作：  
  
-   从 MRSR 站点中删除所有 MT 模板  
  
-   从 MRSR 站点中删除所有协议和合作伙伴配置文件  
  
-   删除所有用户、 角色和部门  
  
-   注销 A4SWIFT BizTalk Server 从 MRSR 站点  
  
#### <a name="the-a4swiftmrsrdepartment-property-is-set-to-an-empty-string-for-a-message-that-did-not-parse"></a>A4SWIFT_MRSRDepartment 属性设置为空字符串作为一条消息，未进行分析。  
 如果消息修复业务流程将路由到 MessageBox 已修复未分析的消息，它会设置[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRDepartment 属性为空字符串，并将其升级。 发送端口不能订阅此属性。  
  
#### <a name="cannot-save-a-department-if-the-sso-service-has-been-stopped"></a>如果 SSO 服务已停止，无法保存部门  
 主 SSO 服务器如果尝试添加系，SSO 服务停止时，你都将收到错误，指示\<machinename\>失败。 检查配置了 SSO 以及 SSO 服务正在该服务器上。  
  
#### <a name="a-department-name-must-not-contain-the-character-"></a>部门名称不得包含字符"~"  
 部门名称包含字符"~"将导致 A4SWIFT 数据库出现问题。  
  
#### <a name="signing-infopath-forms"></a>签名 Infopath 窗体  
 对签名的 InfoPath 窗体需要手动完成。  
  
## <a name="security"></a>安全性

#### <a name="mixing-trusted-and-untrusted-hosts-can-enable-spoofing"></a>混合使用受信任和不受信任主机可以启用欺骗  

 可能从其他不受信任的 SWIFT 绑定消息欺骗[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]托管应用程序。 这是仅一个问题，在混合信任模式下运行时 (受信任的主机和不受信任的主机中运行时，应用程序相同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]组)。 通过使用参与方解析管道组件来标识 SWIFT 绑定消息的源，可以降低此风险。 运行在完全受信任环境中或对于大多数使用方案时，这是不必要的。 应遵循[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]混合时构建安全的应用程序的指导原则受信任和不受信任的主机。 
 
## <a name="miscellaneous"></a>杂项

#### <a name="the-cacheentries-setting-may-be-reset-by-a-setup-program-affecting-performance"></a>CacheEntries 设置可能会重置被安装程序，会影响性能  
 CacheEntries 注册表项确定缓存的业务规则引擎更新服务的规则集的最大数目。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装程序将 CacheEntries 设为 32，默认情况下。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序更改 HKEY_LOCAL_MACHINE\SOFTWARE\\Microsoft \BusinessRules\3.0\CacheEntries 为 512 以获得最佳性能。 但是，在某些情况下，CacheEntries 可能会自动重置。 这可能会影响系统性能。  
  
 规则引擎更新可能会更改 CacheEntries 从 512 到 32 个。 安装规则引擎更新后，手动重置 CacheEntries 为 512，如有必要。  
  
 即使[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将 CacheEntries 32 从设置为 512，卸载[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不重置 CacheEntries 从 512 到 32 个。  
  
 有关详细信息，请参阅 BizTalk Server 帮助中的"规则引擎配置和优化参数"主题。  
  
#### <a name="building-a-pipeline-project-may-result-in-a-large-number-of-warnings"></a>生成管道项目可能会导致大量警告  
 如果您将 SWIFT 汇编程序添加到发送管道或接收管道，到 SWIFT 反汇编程序，然后生成包含这些管道的管道项目可能会收到一系列与管道组件相关的警告。 这些警告指示 Visual Studio 找不到依赖项。 您可以更正导致这些警告，如下所示更改 SWIFTAsm 或 SWIFTDasm 程序集引用文件夹中的复制本地属性的条件：  
  
1.  在解决方案资源管理器的 Visual Studio 中，展开你的管道项目，然后展开**引用**节点。  
  
2.  在引用节点下选择**SWIFTAsm**程序集和/或**SWIFTDasm**程序集。  
  
3.  在属性窗格中的值更改**Copy Local**属性设置为**False**。  
  
4.  右键单击管道项目，然后依次**生成**。  
  
    > [!NOTE]
    >  不应看到有关依赖关系找不到任何警告。   