---
title: 有关安装、 配置和部署的 EDI 和 AS2 解决方案的已知问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dee03f0-2447-4cc2-90f4-e9b73caa0f39
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 406e69cafd4822a0f8f436b471d53c4e815dce32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262797"
---
# <a name="known-issues-with-installation-configuration-and-deployment-of-edi-and-as2-solutions"></a>安装、 配置和部署的 EDI 和 AS2 解决方案的已知的问题
本主题介绍在部署和管理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 解决方案方面的已知问题。  
  
## <a name="blank-strings-were-imported-for-party-properties"></a>为参与方属性导入了空白字符串  
 **症状**  
  
 从绑定文件将 EDI/AS2 绑定导入到 BizTalk 应用程序中时，未导入敏感的参与方属性，如密码或安全/身份验证信息。 这些属性被设置为空白字符串。  
  
 **可能的原因**  
  
 BizTalk Server 不会导入敏感字段的设置。 导入这些设置可能产生安全问题。  
  
 **解决方法**  
  
 必须在将绑定导入到其他计算机中后手动设置 EDI 敏感字段的值。  
  
## <a name="ftp-adapter-is-not-supported-natively-in-64-bit-mode"></a>在 64 位模式下本机不支持 FTP 适配器  
 FTP 适配器无法在本机 64 位模式下运行。 如果您在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中将 FTP 适配器用于 EDI 解决方案，则必须在 64 位 Windows 的 WOW64 上运行此适配器。  
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>某些 EDI/AS2 项目在取消配置后仍处于活动状态  
 在取消对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 Microsoft EDI/AS2 功能的配置后，与 EDI 和 AS2 处理相关的某些 BizTalk Server 项目在 BizTalk 组配置的上下文中将仍处于活动状态。 这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。 因此，即使在取消对 Microsoft EDI/AS2 功能的配置后，您仍然能够执行基本的 EDI 和 AS2 处理。 若要禁用此功能，应禁用、停止或删除与 EDI 和 AS2 处理关联的端口。  
  
## <a name="you-receive-the-error-failed-to-configure-edias2-status-reporting-functionalities"></a>你将收到错误"未能配置 EDI/AS2 状态报告功能"  
 **症状**  
  
 配置 EDI/AS2 运行时状态报告时，您收到“未能配置‘EDI/AS2 状态报告’功能”错误。  
  
 **可能的原因**  
  
 如果以前配置了 BAM 工具，之后又对其取消了配置，则您可能会收到此错误。  
  
 **解决方法**  
  
 在配置 EDI 和/或 AS2 状态报告前配置 BAM 工具。  
  
## <a name="recovering-a-deleted-artifact-from-the-biztalk-edi-application-requires-you-to-reconfigure-the-edias2-runtime"></a>从 BizTalk EDI 应用程序恢复已删除的项目时要求重新配置 EDI/AS2 运行时  
 应避免对您自己的项目使用 BizTalk EDI 应用程序。 此应用程序包含在 EDI/AS2 配置期间部署的 EDI/AS2 项目。 推荐的方法是另外创建一个应用程序，然后向该应用程序添加对 BizTalk EDI 应用程序的引用。 但是，如果从 BizTalk EDI 应用程序中删除了任何 EDI/AS2 项目，则可以通过从组内的每台运行时计算机取消对 BizTalk EDI/AS2 运行时的配置（或通过从组取消对 EDI/AS2 运行时的配置并在每台可访问的运行时计算机上取消对 EDI/AS2 运行时的配置）来从此状态恢复。 建议不要删除自己的数据库或 EDI/AS2 BAM 活动，以防数据丢失。 然后就可以在组内的所有运行时计算机上重新配置 EDI/AS2 运行时，以恢复已删除的 EDI/AS2 项目。  
  
## <a name="numeric-transaction-set-group-control-and-interchange-control-values-may-be-truncated"></a>数字事务集、组控制和交换控制值可能会被减少  
 交换控制编号、事务集参考编号和组控制编号的值范围字段允许您输入超过最大允许值的值。 当您保存该配置时，这些值将被减少为最大值。  
  
 X 12 属性字段的最大值是 999999999。  
  
 EDIFACT 属性字段的最大值是 99999999999999。  
  
## <a name="control-numbers-are-reset-to-1-after-upgrade"></a>控制编号升级后将重置为 1  
 升级后，你可能注意到方的 EDI 属性中显示的所有控制编号已重置为 1 的默认最小值和显示 999999999 (X12) 或 99999999999999 (EDIFACT) 的默认最大值。 任何前缀或后缀值在升级后将保持不变。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]显示要用于控制编号的最小和最大值。 将升级; 过程中保留当前的控制编号但是它不被显示在 EDI 属性的当事方。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 和 AS2 解决方案疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)   
 [BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)   
 [用于优化环境的配置后步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)