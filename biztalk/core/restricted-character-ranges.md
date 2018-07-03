---
title: 受限字符范围 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e12213bf-750e-43a2-998a-949fa4255b73
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb09e0447938c1b394a786293f487de70268cb2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006374"
---
# <a name="restricted-character-ranges"></a>受限的字符范围

## <a name="overview"></a>概述
创建平面文件消息架构时，你可以指示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来阻止特定字符或一系列在任何传出消息中包含的字符。 为此，在 BizTalk 编辑器中，打开要用作目标架构的架构。 选择**架构**节点，然后使用**受限字符**以打开**受限字符**对话框。 输入范围，你想要防止在 BizTalk Server 发送的任何消息中包含的字符，然后单击**确定**。 只要 BizTalk Server 尝试处理中指定的字符**受限字符**生成的目标架构，处理将停止一条错误消息的对话框。  

> [!NOTE]
>  在 BizTalk Server 中，字符范围限制是平面文件扩展的一个功能，因此不适用于 XML 消息。 将来可能为不同类型的消息提供扩展，这些扩展在如何为其支持的消息格式实现字符范围限制方面可能有所不同。  

## <a name="see-also"></a>请参阅  
- [创建平面文件消息架构时的注意事项](../core/considerations-when-creating-flat-file-message-schemas.md)   
- **受限的字符 （平面文件架构的节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
