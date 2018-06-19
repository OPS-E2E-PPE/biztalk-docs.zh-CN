---
title: 无法读取分隔符集，从交换 (R2) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17bdd32e-d43f-4f59-af27-5d3054fd5432
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3836b218ac3596bef25edb29eaf72c38f65b6e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239077"
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a>无法从交换 (R2) 读取分隔符集
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|无法从交换中读取分隔符集。 根节点中缺少属性 DelimiterSetSerializedData。|  
  
## <a name="explanation"></a>解释  
 此错误表明交换不包含分隔符集值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   按照如下方式将分隔符集值添加到交换中：  
  
    1.  打开消息。  
  
    2.  确定交换中是否存在 UNA 段。 如果没有 UNA 段，请咨询合作伙伴以将 UNA 段添加到交换中。  
  
-   按照如下方式输入 EfactDelimiters 管道属性的分隔符值：  
  
    1.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，右键单击使用你要设置其属性的管道的接收位置或发送端口。 单击 **“属性”**。  
  
    2.  单击你要设置其属性的管道旁的省略号按钮 (…)。  
  
    3.  输入以逗号分隔列表形式的 UNA 分隔符（对于 UNA1、UNA2、UNA3、UNA4、UNA5 和 UNA6）的值，根据需要更改默认值。 默认值为，如下所示： 0x3A、 0x2B、 0x2C、 0x3F、 0x20、 0x27。  
  
    4.  单击 **“确定”**。