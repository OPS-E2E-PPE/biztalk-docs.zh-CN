---
title: 使用 Visual Studio 的 MSBUILD 集成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aedcabf7-b2cf-482a-9ade-7311e104bff9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01b0f59d73c48dba994b0c57cae3b4c697e426b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264536"
---
# <a name="msbuild-integration-with-visual-studio"></a>与 Visual Studio 的 MSBUILD 集成
Visual Studio 使用 MSBUILD 项目文件格式来存储有关托管项目包括 BizTalk 项目的生成信息。 添加和更改通过 Visual Studio 的项目设置将反映每个项目生成的.btproj 文件中。 Visual Studio 使用 MSBUILD 的托管的实例生成 BizTalk 项目，这意味着在 Visual Studio 或从命令行中，具有相同的结果，可以生成 BizTalk 项目。  
  
 有关 MSBUILD 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=193567 ](http://go.microsoft.com/fwlink/?LinkId=193567)。  
  
 以下过程演示如何使用 MSBUILD 来生成示例 BizTalk 项目，从命令行。  
  
## <a name="to-build-a-biztalk-project-from-a-command-line"></a>若要生成命令行从 BizTalk 项目  
  
1.  启动**Visual Studio 命令提示符**。  
  
2.  切换到项目目录，然后运行 MSBUILD 命令以生成 BizTalk 解决方案。  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!NOTE]
    >  该解决方案可能包含 BizTalk 和非 BizTalk 项目中，如C#类库。