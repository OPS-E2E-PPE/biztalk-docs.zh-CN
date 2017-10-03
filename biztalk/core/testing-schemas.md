---
title: "测试架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2e28b7c-9d0c-4336-8bee-4599d41a57f4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20879925ff98d5c5d6ca7d0c9ebcf11853239bba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="testing-schemas"></a>测试架构
在创建架构之后，您可能希望验证该架构的 XML 结构符合您的要求。 您可以对架构执行以下三种操作以进行验证：  
  
-   **实例生成**。 此操作将从架构生成实例消息，创建要显示由该架构指定的 XML 元素和属性的测试数据。  
  
-   **架构验证**。 此操作将验证架构的内部一致性，确保它符合 XML 架构定义 (XSD) 语言架构标准。  
  
-   **实例验证**。 此操作将依据架构验证给定的实例消息。  
  
 对于在生产环境中使用架构之前测试该架构，所有这三种操作都非常有用。  
  
 本部分较详细地介绍了这些操作。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何验证在 Visual Studio 中的架构](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [如何验证实例消息](../core/how-to-validate-instance-messages.md)  
  
-   [如何生成实例消息](../core/how-to-generate-instance-messages.md)