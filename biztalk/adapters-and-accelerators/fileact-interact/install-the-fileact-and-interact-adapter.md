---
title: 安装 FileAct 和 InterAct 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf387d59-373b-4151-9dfd-30c511978862
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5ee288b9772b7585fe972a4335e3cf8c5595024
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989382"
---
# <a name="install-the-fileact-and-interact-adapter"></a>安装 FileAct 和 InterAct 适配器
本部分提供安装说明[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]– 对于 SWIFT。 安装适配器之前，必须安装必备软件。  
  
## <a name="prerequisites"></a>必要條件  

* 使用的是本地管理员组的成员和 BizTalk Server Administrators 组的成员的帐户登录
  
## <a name="step-1-install-biztalk-server-and-configure-bam"></a>步骤 1： 安装 BizTalk Server 并配置 BAM

1. 安装[BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md)，或[BizTalk Server 2013 R2 / 2013年](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)，并安装业务活动监视 (BAM)。

2. 配置[BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md)，并配置业务活动监视 (BAM)。
  
3. 请确保有足够的安全特权访问[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 [为 BizTalk Server 的最低安全权限](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)是一个不错的资源。
  
## <a name="step-2-install-biztalk-accelerator-for-swift-a4swift"></a>步骤 2： 安装 BizTalk Accelerator for SWIFT (A4SWIFT)  

安装和配置[BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md)。

  
## <a name="step-3-install-swiftalliance-gateway-sag"></a>步骤 3： 安装 SWIFTAlliance 网关 （压降）  
 安装 FileAct 和 InterAct 适配器之前，请创建压降消息合作伙伴、 终结点和路由规则，并测试压降连接，可以在其中安装 FileAct 和 InterAct 适配器的计算机。

请参阅[ https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway ](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway) SWIFTAlliance 网关上的特定详细信息。  

## <a name="step-4-install-the-biztalk-fileact-and-interact-adapters"></a>步骤 4： 安装 BizTalk FileAct 和 InterAct 适配器  
  
1. 运行**Setup.exe**以管理员身份开始安装。  
  
2. 选择“安装”。  
  
3. 输入用户名和组织名称，然后选择**下一步**。  
  
4. **接受**许可协议。
  
5. 上**安装选项**页上，执行下列操作之一：  
  
   - 选择**完成**选项来安装所有组件的 FileAct 和 InterAct 适配器。  
  
   - 选择**自定义**选项以选择要安装哪些组件。  
  
     验证安装位置，或选择**浏览**来选择不同的安装位置。 选择“下一步” 。  
  
6. 上**摘要**页上，选择**安装**安装列出的组件。  
  
   > [!NOTE]
   >  当**运行配置向导**是选择 （默认值）， **Microsoft BizTalk FileAct 和交互适配器配置**向导会自动运行时选择**完成**.  
  
7. 安装完成后，选择**完成**。 

## <a name="next-steps"></a>后续步骤

[配置 FileAct 和 InterAct 适配器](../../adapters-and-accelerators/fileact-interact/configure-the-fileact-and-interact-adapter.md)  
[示例 InterAct 和 FileAct 消息](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)  
[卸载或修复 FileAct 和 InterAct 适配器](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[阅读安装过程中的已知问题](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
  
## <a name="see-also"></a>请参阅  
[FileAct 和 InterAct 适配器入门](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)  
[了解 FileAct 和 InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)