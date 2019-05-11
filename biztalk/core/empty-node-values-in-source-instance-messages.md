---
title: 源中的空节点值实例消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76f9d7c8-5a82-41e9-9077-7b1ddd80a837
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afaf714e3c979576939ebef8fdd39f283828cab7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350018"
---
# <a name="empty-node-values-in-source-instance-messages"></a>源实例消息中的空节点值
可能的有时你不想时中的所有架构节点的内容时测试映射。  

## <a name="ceate-empty-node-values"></a>请空节点值  

1. 生成实例数据使用 BizTalk 编辑器。 有关生成实例数据的详细信息，请参阅[如何生成实例消息](../core/how-to-generate-instance-messages.md)。  

2. 在文本编辑器中打开输入的实例消息从用于你想要为空，元素和属性中删除数据，然后将修改后的实例文件保存。  

3. 配置 BizTalk 映射器以使用刚刚修改过的架构验证和测试的文件。 在为架构属性窗口中设置该文件。 有关设置属性的详细信息，请参阅**映射文件属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>请参阅  
- [如何生成实例消息](../core/how-to-generate-instance-messages.md)   
- **架构属性参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
