---
title: "已知 Issues5 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, known issues
- BizTalk Accelerator for SWIFT, known issues
- known issues
ms.assetid: 0f1ec7dd-9e74-479a-bdc8-ab9c4397c992
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1356209f700fc7ceff220f4b0f8fcd3dd67db07
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues"></a>已知问题
本部分包含有用信息来帮助你避免与错误[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]。 已知问题归为以下几个方面：  
  
## <a name="message-repair-and-new-submission"></a>消息修复和新的提交

#### <a name="printing-of-a-repair-document-is-recorded-in-the-history-log-even-if-canceled"></a>在历史记录日志中记录的修复文档的打印，即使取消  
 如果运行修复收件箱中的文档打印命令，然后取消打印打印仍将输入到历史记录日志。 发生这种情况是当你打开文档后，在要修复其[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，单击文件菜单上的打印命令，然后单击打印对话框中的取消。 历史记录日志中的条目，则应将其忽略。  
  
#### <a name="a-duplicate-signature-can-cause-an-xlangs-error-message"></a>重复的签名可能会导致 XLANG/s 错误消息  
 当一个验证程序使用相同的证书作为 repairer[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]挂起消息，并指示不允许重复的签名对错误消息中。 但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]还会生成与 XLANG/s，XLANG/s 服务已被挂起，该值指示事件源的另一个错误消息。 可以忽略此消息。  
  
#### <a name="message-size-can-affect-repair-performance"></a>消息大小可能会影响修复性能  
 如果你尝试修复非常大的 XML 文件，当你打开中的 XML 文件时，系统性能会大大降低[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]消息类型窗体。 内存消耗可能会增加，可能会降低 CPU 占用率，进程可能会失败并出现错误，指示没有足够的存储已可用于完成该操作。  
  
#### <a name="the-last-signature-used-to-sign-a-message-successfully-will-be-authenticated-by-authenticate-signatures"></a>用于已成功对消息进行签名的最后一个签名将通过身份验证的签名进行身份验证  
 单击身份验证的签名按钮[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中只是如果您已经注册该窗体阶段验证的签名。 否则，它验证的签名为上一阶段，如果没有一个，并发布以下错误：  
  
 签名用户未正确配置为部门 < department_name > 中 < stage_name > 角色。  
  
 例如，假设你在验证阶段之后立即处于批准阶段。 如果尚未登录窗体为审批者，然后单击进行身份验证签名，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]进行身份验证验证程序使用，不是审批者的签名的签名并将前面的错误。  

#### <a name="a4swift-cleanup-tool-doesnt-delete-templates"></a>A4SWIFT 清理工具不会删除模板  
 A4SWIFT 清理工具不会执行以下操作：  
  
-   从 MRSR 站点中删除所有 MT 模板  
  
-   从 MRSR 站点中删除所有协议和合作伙伴配置文件  
  
-   删除所有用户、 角色和部门  
  
-   从 MRSR 站点 A4SWIFT BizTalk Server 中注销  
  
#### <a name="the-a4swiftmrsrdepartment-property-is-set-to-an-empty-string-for-a-message-that-did-not-parse"></a>A4SWIFT_MRSRDepartment 属性设置为空字符串作为一条消息，未进行分析  
 在消息修复业务流程将路由到 MessageBox 未分析的消息已修复，它会将设置[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRDepartment 属性设置为一个空字符串并将其升级。 发送端口将不能订阅此属性上。  
  
#### <a name="cannot-save-a-department-if-the-sso-service-has-been-stopped"></a>如果 SSO 服务已停止，无法保存部门  
 主 SSO 服务器如果你尝试添加一个部门，SSO 服务停止时，你都将收到错误，该值指示\<machinename\>失败。 请检查是否正确配置了 SSO 以及 SSO 服务是否正在该服务器上运行。  
  
#### <a name="a-department-name-must-not-contain-the-character-"></a>部门名称不能包含字符"~"  
 包含字符的部门名称"~"将导致 A4SWIFT 数据库时出现的问题。  
  
#### <a name="signing-infopath-forms"></a>签名 Infopath 窗体  
 对签名的 InfoPath 窗体需要手动完成。  
  
## <a name="security"></a>安全性

#### <a name="mixing-trusted-and-untrusted-hosts-can-enable-spoofing"></a>混合使用受信任和不受信任主机可以启用欺骗  

 有可能为欺骗从其他不受信任的 SWIFT 绑定消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]托管应用程序。 这是只是问题，在混合信任模式下运行时 (受信任的主机和不受信任的主机中运行时，应用程序相同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]组)。 通过使用参与方解析管道组件标识 SWIFT 绑定消息的源，可以缓解此风险。 运行在完全受信任环境中或对于大多数使用情况方案时，这是不必要的。 应遵循[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]混合时构建安全应用程序的指导原则受信任和不受信任的主机。 
 
## <a name="miscellaneous"></a>杂项

#### <a name="the-cacheentries-setting-may-be-reset-by-a-setup-program-affecting-performance"></a>CacheEntries 设置重置被安装程序，会对性能影响  
 CacheEntries 注册表项确定的最大 ruleset 由业务规则引擎更新服务缓存数。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装程序默认情况下将 CacheEntries 设为 32。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序更改 HKEY_LOCAL_MACHINE\SOFTWARE\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]\BusinessRules\3.0\CacheEntries 为 512 以获得最佳性能。 但是，在某些情况下，CacheEntries 可能被自动重新设置。 这可能会影响系统性能。  
  
 规则引擎更新可能会变为 CacheEntries 从 512 32。 在安装的规则引擎更新后, 手动重置 CacheEntries 为 512，如有必要。  
  
 即使[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将从 32 CacheEntries 设置为 512，卸载[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不重置 CacheEntries 从 512 为 32。  
  
 有关详细信息，请参阅 BizTalk Server 帮助中的"规则引擎配置和优化参数"主题。  
  
#### <a name="building-a-pipeline-project-may-result-in-a-large-number-of-warnings"></a>生成管道项目可能会导致大量的警告  
 当你将 SWIFT 汇编程序添加到发送管道或 SWIFT 拆装器接收管道，然后生成包含这些管道的管道项目，你可能会收到警告的管道组件相关的一系列。 这些警告指示 Visual Studio 找不到依赖项。 您可以更正导致通过更改中的引用文件夹中，SWIFTAsm 或 SWIFTDasm 程序集的复制本地属性，如下所示的这些警告的条件：  
  
1.  在解决方案资源管理器的 Visual Studio 中，展开你的管道项目，然后展开**引用**节点。  
  
2.  在引用节点下选择**SWIFTAsm**程序集和/或**SWIFTDasm**程序集。  
  
3.  在属性窗格中的值更改**Copy Local**属性**False**。  
  
4.  右键单击你管道的项目，并依次**生成**。  
  
    > [!NOTE]
    >  不应看到有关依赖关系找不到任何警告。   