---
title: JMS MQRFH2 示例依赖关系和强密钥名称定义 |Microsoft Docs
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
ms.openlocfilehash: c7079bc7475fa8310d64ff6925dd89e348afc195
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261538"
---
# <a name="jms-mqrfh2-sample-dependencies-and-strong-key-name-definition"></a>JMS MQRFH2 示例依赖关系和强密钥名称定义
Visual Studio 项目 ESB。JMS。PipelineComponents 取决于以下文件夹：  
  
-   \<BizTalk Server 安装目录\>。 此文件夹提供了对以下命名空间的访问：  
  
    -   **Microsoft::BizTalk::Message::Interop**  
  
    -   **Microsoft::BizTalk::Component::Interop**  
  
## <a name="the-strong-name-key-definition"></a>强名称密钥定义  
 通常情况下，强名称密钥定义驻留在的 AssemblyInfo.cpp 文件中。 但是，这将与冲突C++读取的 AssemblyInfo.cpp 文件后，编译器将添加到该程序集的清单文件。 此冲突会阻止任何尝试将该文件放在全局程序集缓存中。 相反，链接器控件的强名称密钥文件通过指定密钥文件位于.../../../../../../ Keys/Microsoft.Practices.ESB.snk。 若要编辑此值，导航到以下选项设置：  
  
 ESB。JMS。架构  
  
 \- 项目  
  
 \- -属性  
  
 \- --配置属性  
  
 \- ---链接器  
  
 \- ----高级  
  
 \- -密钥文件  
  
> [!NOTE]
>  如果构造 JMS 管道组件，则必须编辑 AssemblyInfo.cpp 文件以删除对强名称密钥文件，任何引用，如前面所述。 完成该操作后，编辑**密钥文件**选项链接器的高级属性中指定的路径和强名称密钥文件的名称。