---
title: "创建架构项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67e6278c-a597-4700-80bf-48e37aaa9c05
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58017b24f7b7464745f48cc202734217dfb327d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-schema-project"></a>创建架构项目
若要创建架构项目：  
  
1.  在 Visual Studio 中，创建 SWIFT MX 架构 BizTalk 项目。  
  
2.  将相应 MX 架构 （从 ISO20022 站点下载），您想要测试，添加到此项目。  
  
3.  如果你想要执行的消息修复功能和新提交功能对于上面的 MX 消息，则还与上面的消息类型相对应的信封架构必须将其部署其他继续执行步骤 6。  
  
    > [!NOTE]
    >  有关如何生成 MX 信封架构的信息，请参阅窗体生成器文档。  
  
4.  将信封架构添加到 SWIFT MX 架构项目。  
  
5.  在 BizTalk 编辑器中打开信封架构并将提升"CorrelationToken"和"IsNewSubmission"属性。 右键单击上面的字段，然后单击**Promote-> 快速升级**来升级这些属性。  
  
    > [!NOTE]
    >  有关如何升级的架构中的属性的详细信息，请参阅 BizTalk Server 文档。  
  
6.  创建密钥文件 （使用 Sn-k key.snk），然后将其分配给项目以创建强名称程序集。  
  
7.  生成然后部署项目。