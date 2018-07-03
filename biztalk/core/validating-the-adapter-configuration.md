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
ms.openlocfilehash: 0d7fa3af1fa0116f859f0d3f39f2235be38cbc0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008126"
---
# <a name="validating-the-adapter-configuration"></a>正在验证适配器配置
同时添加接收位置和发送端口，您将需要配置自定义属性中的**\<**<em>适配器名称</em> **\>传输属性**对话框。 AdapterHarness 项目中的 XSD 架构文件用于定义这些属性。  
  
 架构配置的验证分三种情况：  
  
1.  显示保存的配置时，在将保存的 XML 文档加载到属性页之前，适配器框架会根据架构验证该文档。 该框架假定文档无效表示配置架构定义发生了更改。 只有有效的文档才能加载到属性页中。  
  
2.  保存配置，如果适配器实现时**IAdapterConfigValidation**接口，该框架传递到适配器构造的 XML 文档序列化属性页数据。 然后适配器处理该文档。 出现任何错误都会产生异常，这些异常由框架捕获并显示给用户。 任何缺少的值或生成的值都会在验证过程中生成。 使用\<可浏览 show ="false"\>修饰可取消其中一个条目显示在属性网格中，即使此值出现在 XML 实例。  
  
3.  保存配置以将值放入数据库时，框架将再次根据架构验证 XML 文档。 这可确保只保存有效数据。  
  
## <a name="see-also"></a>请参阅  
 [适配器设计问题](../core/adapter-design-issues.md)