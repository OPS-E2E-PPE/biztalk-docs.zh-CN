---
title: JMS MQRFH2 示例依赖关系和强密钥名称定义 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3a5cdce-dcdf-48df-91a5-8cf2afce9255
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f3e2f76a972f851322f82f2e89b285db907d799
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976491"
---
# <a name="jms-mqrfh2-sample-dependencies-and-strong-key-name-definition"></a>JMS MQRFH2 示例依赖关系和强密钥名称定义
Visual Studio 项目 ESB 中。JMS。PipelineComponents 取决于以下文件夹：  
  
-   \<BizTalk Server 安装目录\>。 此文件夹提供了对以下命名空间的访问：  
  
    -   **Microsoft::BizTalk::Message::Interop**  
  
    -   **Microsoft::BizTalk::Component::Interop**  
  
## <a name="the-strong-name-key-definition"></a>强名称密钥定义  
 通常情况下，强名称密钥定义驻留在的 AssemblyInfo.cpp 文件中。 但是，这会与 c + + 清单文件，它读取的 AssemblyInfo.cpp 文件之后，编译器将添加到程序集冲突。 此冲突将阻止任何尝试将文件放在全局程序集缓存中。 相反，链接器将通过指定密钥文件位于控制强名称密钥文件.../../../../../../ Keys/Microsoft.Practices.ESB.snk。 若要编辑此值，导航到以下选项设置：  
  
 ESB。JMS。架构  
  
 \- 项目  
  
 \--属性  
  
 \---配置属性  
  
 \----链接器  
  
 \-----高级  
  
 \------密钥文件  
  
> [!NOTE]
>  如果你构造 JMS 管道组件，则必须编辑 AssemblyInfo.cpp 文件，以删除对的强名称密钥文件的任何引用，如前面所述。 完成该操作后，编辑**密钥文件**链接器的高级属性中的选项以指定的路径和强名称密钥文件的名称。