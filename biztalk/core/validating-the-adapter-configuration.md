---
title: 正在验证适配器配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc36a885614eac72f70e588fefe4731717322019
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279550"
---
# <a name="validating-the-adapter-configuration"></a>正在验证适配器配置
同时添加接收位置和发送端口，您将需要配置自定义属性中的**\<**<em>适配器名称</em> **\>传输属性**对话框。 AdapterHarness 项目中的 XSD 架构文件定义这些属性。  
  
 配置架构验证发生在三个部分：  
  
1.  在显示时保存的配置，适配器框架将文档加载到属性页之前会验证针对该架构保存的 XML 文档。 框架将假定不是有效的文档指示配置架构定义中的更改。 只有有效的文档加载到属性页。  
  
2.  保存配置，如果适配器实现时**IAdapterConfigValidation**接口，该框架传递到适配器构造的 XML 文档序列化属性页数据。 然后，适配器处理文档。 任何错误应生成的异常由框架捕获并向用户显示。 应在验证过程中生成任何缺失或生成值。 使用\<可浏览 show ="false"\>修饰可取消其中一个条目显示在属性网格中，即使此值出现在 XML 实例。  
  
3.  在保存之前将值放入数据库的配置时，框架将再次验证针对该架构的 XML 文档。 这可确保仅有效的数据将保留。  
  
## <a name="see-also"></a>请参阅  
 [适配器设计问题](../core/adapter-design-issues.md)