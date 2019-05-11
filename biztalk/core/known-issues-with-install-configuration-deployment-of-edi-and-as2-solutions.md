---
title: 有关安装、 配置和部署的 EDI 和 AS2 解决方案的已知问题 |Microsoft Docs
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
ms.openlocfilehash: c376709ab9abcd5859e122d9c70a413f4fc89054
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329133"
---
# <a name="known-issues-with-installation-configuration-and-deployment-of-edi-and-as2-solutions"></a>安装、 配置和部署的 EDI 和 AS2 解决方案的已知的问题
本主题介绍了部署和管理的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 和 AS2 解决方案。  
  
## <a name="blank-strings-were-imported-for-party-properties"></a>为参与方属性导入空白字符串  
 **症状**  
  
 当您从绑定文件将 EDI/AS2 绑定导入 BizTalk 应用程序上时，未导入敏感的参与方属性，如密码或安全/身份验证信息。 这些属性被设置为空白字符串。  
  
 **可能的原因**  
  
 BizTalk Server 不会导入敏感字段的设置。 导入这些设置可以创建一个安全问题。  
  
 **解决方法**  
  
 导入到另一台计算机上的绑定后，必须手动设置 EDI 敏感字段的值。  
  
## <a name="ftp-adapter-is-not-supported-natively-in-64-bit-mode"></a>FTP 适配器不支持本机 64 位模式  
 FTP 适配器不能在本机 64 位模式下运行。 如果使用 FTP 适配器在 EDI 解决方案中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，必须在 64 位 Windows 上在 WOW64 上运行它。  
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>某些 EDI/AS2 项目是取消配置后仍处于活动状态  
 取消配置的 Microsoft edi/as2 功能后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，与 EDI 和 AS2 处理相关的某些 BizTalk Server 项目仍将在 BizTalk 组配置的上下文中处于活动状态。 这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。 因此，您将仍然能够执行基本的 EDI 和 AS2 处理后取消 Microsoft EDI/AS2 功能的配置。 若要禁用此功能，应禁用、 停止或删除与 EDI 和 AS2 处理关联的端口。  
  
## <a name="you-receive-the-error-failed-to-configure-edias2-status-reporting-functionalities"></a>收到错误"未能配置 'EDI/AS2 状态报告' 功能"  
 **症状**  
  
 在配置 EDI/AS2 运行时状态报告时，你将收到错误"未能为配置 EDI/AS2 状态报告 ' 功能"。  
  
 **可能的原因**  
  
 如果以前的配置，然后取消配置 BAM 工具时，会收到此错误。  
  
 **解决方法**  
  
 配置 EDI 和/或 AS2 状态报告前配置 BAM 工具。  
  
## <a name="recovering-a-deleted-artifact-from-the-biztalk-edi-application-requires-you-to-reconfigure-the-edias2-runtime"></a>从 BizTalk EDI 应用程序恢复已删除的项目，需要重新配置 EDI/AS2 运行时  
 应避免使用 BizTalk EDI 应用程序用于自己的项目。 此应用程序包含在 edi/as2 配置期间部署的 EDI/AS2 项目。 建议的方法是创建单独的应用程序并添加对 BizTalk EDI 应用程序到应用程序的引用。 但是，如果从 BizTalk EDI 应用程序中删除任何 EDI/AS2 项目，则可以恢复从该状态由取消配置 BizTalk edi/as2 运行时从组中每个运行时计算机 （或取消配置 EDI/AS2 运行时从组和取消配置的EDI/AS2 运行时在每个可访问运行时计算机上）。 建议您不要删除自己的数据库或 EDI/AS2 BAM 活动，以防止数据丢失。 然后可以重新配置要恢复已删除的 edi/as2 项目的组中的所有运行时计算机上的 EDI/AS2 运行时。  
  
## <a name="numeric-transaction-set-group-control-and-interchange-control-values-may-be-truncated"></a>数字事务集、 组控制和交换控制值可能会被截断  
 交换控制编号的值范围字段，事务集参考编号和组控制编号允许您输入超过最大允许值的值。 当您保存该配置时，这些值将被截断的最大值。  
  
 适用于 X12 的最大值属性字段是 999999999。  
  
 EDIFACT 属性字段的最大值是 99999999999999。  
  
## <a name="control-numbers-are-reset-to-1-after-upgrade"></a>控制编号重置为 1 的升级后  
 升级后，你可能会注意到所有显示的参与方 EDI 属性中的控制编号已重置为 1 的默认最小值和显示默认最大值为 999999999 (X12) 或 99999999999999 (EDIFACT)。 任何前缀或后缀值将升级后保持相同。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 显示要用于控制编号的最小值和最大值。 将升级; 过程中保留当前的控制编号但是它不被显示在参与方的 EDI 属性。  
  
## <a name="see-also"></a>请参阅  
 [EDI 和 AS2 解决方案的疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)   
 [BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)   
 [用于优化环境的配置后步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)