---
title: 已知问题的安装 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2f80ff9-b37c-49f8-8250-fcf3cec4c0fc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4e9197d2b3c448b4fd9cc42c0cdeb929917061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204541"
---
# <a name="installation-known-issues"></a>安装的已知问题
有用的信息来帮助你避免安装问题。  
  
## <a name="prerequisites-for-installing-btahl7"></a>安装 BTAHL7 的先决条件  
 安装的先决条件[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]如下：  
  
-   基本组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，包括企业单一登录 (SSO)、 组和运行时，应配置。  
  
-   安装和配置 BTAHL7 用户必须是 BizTalk 管理员组的成员和存储 BTAHL7 数据的 SQL 服务器上的管理员组的成员。
  
## <a name="sql-server-mixed-mode-not-supported"></a>不支持的 SQL Server 混合的模式  
[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]不在混合模式下支持 SQL Server。  
  
## <a name="repair-does-not-work-from-uninstallchange"></a>修复卸载/更改中无法正常工作  
如果启用了用户访问控制 (UAC)，并且你尝试使用控制面板修复安装，则修复失败。 

Microsoft 建议你保留支持 UAC。

 **解决方法**  
  
 运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]setup.exe，然后选择**修复**。  
  
## <a name="see-also"></a>另请参阅  
[安装或升级 Microsoft BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)