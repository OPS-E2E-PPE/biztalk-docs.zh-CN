---
title: 地址长度无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e16eb6-e77e-4361-ac91-0730004c4433
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8da5e041ad861557817491695f0d7972a207864a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008470"
---
# <a name="invalid-address-length"></a>地址长度无效
## <a name="details"></a>详细信息  

|                 |                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------|
|  产品名称   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| 产品版本 |                 [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                  |
|    事件 ID     |                                              0                                              |
|  事件源   |                                              0                                              |
|    组件    |                                              0                                              |
|  符号名称  |                                              0                                              |
|  消息正文   | 地址长度无效;指定的地址长度为{0}字符，限制是{1}字符 |

## <a name="explanation"></a>解释  
 为 WCF 传输提供的地址超出 255 个字符的最大长度。 这是 BizTalk Server（而不是 WCF）规定的限制。  

## <a name="user-action"></a>用户操作  
 使用以下过程配置有效地址。  

#### <a name="to-configure-a-valid-address"></a>配置有效地址  

1. 单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。  

3. 找到你的应用程序，然后找到您的传输。  

4. 右键单击传输名称。  

5. 单击 **“属性”**。  

6. 在端口**类型**列表中，选择正确的端口。  

7. 单击**配置**。  

8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。  

9. 在中**地址 (URI)** 文字框中，确保地址不超过 255 个字符的最大长度。
