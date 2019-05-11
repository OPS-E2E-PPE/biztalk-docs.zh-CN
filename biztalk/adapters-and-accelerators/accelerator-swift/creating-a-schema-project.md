---
title: 创建架构项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67e6278c-a597-4700-80bf-48e37aaa9c05
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a6419c008a95277256c75fbd0b7d6dda388061f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378467"
---
# <a name="creating-a-schema-project"></a>创建架构项目
若要创建架构项目：  
  
1.  在 Visual Studio 中，创建 SWIFT MX 架构 BizTalk 项目。  
  
2.  将相应 MX 下载的架构 （从 ISO20022 站点），你要测试，添加到此项目。  
  
3.  如果你想要执行上述 MX 消息的消息修复和新提交功能然后也与上面的消息类型相对应的信封架构需要部署其他继续执行步骤 6。  
  
    > [!NOTE]
    >  有关如何生成 MX 信封架构的信息，请参阅窗体生成器文档。  
  
4.  将信封架构添加到 SWIFT MX 架构项目。  
  
5.  在 BizTalk 编辑器中打开信封架构并将提升"CorrelationToken"和"IsNewSubmission"属性。 右键单击上述字段，然后单击**提升-> 快速升级**以升级这些属性。  
  
    > [!NOTE]
    >  有关如何升级属性架构的详细信息，请参阅 BizTalk Server 文档。  
  
6.  创建密钥文件 （使用 Sn – k key.snk），并再将其分配给项目创建强名称程序集。  
  
7.  生成，然后部署该项目。