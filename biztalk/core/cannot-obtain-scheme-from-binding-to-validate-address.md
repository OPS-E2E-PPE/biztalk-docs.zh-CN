---
title: 无法从绑定以验证地址获取方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b002084a-63ae-4685-8ce3-88cc6489e19e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d42116dff2ad72b4d076b7c6e5303f1d8636e9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358063"
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a>无法从绑定以验证地址获取方案
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |               无法从绑定以验证地址获取方案。               |
  
## <a name="explanation"></a>解释  
 已指定的传输绑定元素没有一种方案。  
  
## <a name="user-action"></a>用户操作  
 请确保传输绑定元素拥有有效的方案，或选择一个有效的传输绑定元素。 如果使用自定义绑定时，请确保指定有效的传输绑定元素。  
  
 有关其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [配置 WCF-Custom 适配器](../core/configuring-the-wcf-custom-adapter.md)