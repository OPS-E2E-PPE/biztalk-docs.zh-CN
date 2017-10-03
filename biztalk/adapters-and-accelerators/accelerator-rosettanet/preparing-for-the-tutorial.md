---
title: "BizTalk Server 中的 RosettaNet 环回教程的先决条件 |Microsoft 文档"
description: "单步执行 RosettaNet 快捷键 (BTARN) BizTalk Server 中的环回本教程的先决条件"
caps.latest.revision: "9"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e26696c-86c5-448b-9cd6-bfd4a279151a
ms.author: mandia
ms.openlocfilehash: 9767f7823e80d4de67345ba0fbf59c1435adb8e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-for-the-tutorial"></a>准备教程

## <a name="prerequisites"></a>先决条件
之前开始环回教程：
  
-   [安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)快捷键。 你可能需要将 btarnhttpreceive 虚拟目录添加到在 SharePoint 管理中心内的 Windows SharePoint 托管的路径排除列表。  
  
-   必须确保 BizTalkServerIsolatedHost 和 BizTalkServerApplication 主机具有**受信任的身份验证**选项处于启用状态。 若要验证，打开 BizTalk Server 管理控制台中，然后展开**主机**。 右键单击主机，选择**属性**，并检查**受信任的身份验证**如果未启用。  

    如果你有多个主机实例，然后删除所有只保留一个主机实例。 例如，删除 BizTalk Server 隔离的主机实例，并保留 BizTalkServerApplication 主机实例）。 此允许你选择**受信任的身份验证**上与关联的主机的实例，然后重新创建额外的主机实例。  
  
## <a name="next-step"></a>下一步
 [步骤 1： 创建主组织](step-1-create-the-home-organization.md)