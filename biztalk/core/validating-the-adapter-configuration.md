---
title: "正在验证适配器配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c03054332e0cd2117c1219afec3dd1aa0a09d6bd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="validating-the-adapter-configuration"></a>正在验证适配器配置
时添加的接收位置和发送端口，你将需要配置在你自定义属性 **\<** *适配器名称* **\>传输属性**对话框。 AdapterHarness 项目中的 XSD 架构文件用于定义这些属性。  
  
 架构配置的验证分三种情况：  
  
1.  显示保存的配置时，在将保存的 XML 文档加载到属性页之前，适配器框架会根据架构验证该文档。 该框架假定文档无效表示配置架构定义发生了更改。 只有有效的文档才能加载到属性页中。  
  
2.  保存配置时，如果适配器实现时**IAdapterConfigValidation**接口，框架将传递给构造的 XML 文档的适配器从序列化的属性页数据。 然后适配器处理该文档。 出现任何错误都会产生异常，这些异常由框架捕获并显示给用户。 任何缺少的值或生成的值都会在验证过程中生成。 使用\<可浏览显示 ="false"\>修饰取消显示一个条目，在属性网格中，即使值出现在 XML 实例。  
  
3.  保存配置以将值放入数据库时，框架将再次根据架构验证 XML 文档。 这可确保只保存有效数据。  
  
## <a name="see-also"></a>另请参阅  
 [适配器设计问题](../core/adapter-design-issues.md)