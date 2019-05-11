---
title: 在 BizTalk Server 中 RosettaNet Loopback 教程的先决条件 |Microsoft Docs
description: 单步执行 BizTalk Server 中的 RosettaNet 加速器 (BTARN) 的 Loopback 教程的先决条件
caps.latest.revision: 9
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e26696c-86c5-448b-9cd6-bfd4a279151a
ms.author: mandia
ms.openlocfilehash: 807aa4002f08c9cb9f40f2bc6dad216bc2d730a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282621"
---
# <a name="prepare-for-the-tutorial"></a>准备此教程

## <a name="prerequisites"></a>先决条件
Loopback 教程开始： 前
  
-   [安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)快捷键。 您可能需要将 btarnhttpreceive 虚拟目录添加到在 SharePoint 管理中心内 Windows SharePoint 管理的路径排除列表。  
  
-   确保 BizTalkServerIsolatedHost 和 BizTalkServerApplication 主机已**受信任验证**选项处于启用状态。 若要验证，打开 BizTalk Server 管理控制台中，然后展开**主机**。 右键单击该主机中，选择**属性**，并检查**受信任验证**如果未启用。  

    如果您有多个主机实例，则删除所有只保留一个主机实例。 例如，删除 BizTalk Server 独立主机实例，并保留 BizTalkServerApplication 主机实例）。 这使你可以选择**受信任验证**与关联的实例，并重新创建其他主机实例的主机上。  
  
## <a name="next-step"></a>下一步
 [步骤 1：创建本组织](step-1-create-the-home-organization.md)