---
title: 安装的已知问题 |Microsoft Docs
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
ms.openlocfilehash: 3c95a8de4437f2ae52c01f77fbfe6e4ff0d559d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65300079"
---
# <a name="installation-known-issues"></a>安装的已知问题
有用的信息可帮助你避免出现安装问题。  
  
## <a name="prerequisites-for-installing-btahl7"></a>安装 BTAHL7 的先决条件  
 安装的先决条件[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]包括以下：  
  
- 基本组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]（包括企业单一登录 (SSO)、 组和运行时），应配置。  
  
- 安装和配置 BTAHL7 用户必须是 BizTalk Administrators 组的成员和 BTAHL7 数据的存储位置的 SQL Server 上管理员组的成员。
  
## <a name="sql-server-mixed-mode-not-supported"></a>不支持的 SQL Server 混合的模式  
[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]不在混合模式下支持 SQL Server。  
  
## <a name="repair-does-not-work-from-uninstallchange"></a>修复卸载/更改中无法正常工作  
如果启用用户访问控制 (UAC)，并尝试使用控制面板修复安装，修复将失败。 

Microsoft 建议您将在启用 UAC。

 **解决方法**  
  
 运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]setup.exe，并选择**修复**。  
  
## <a name="see-also"></a>请参阅  
[安装或升级 Microsoft BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)