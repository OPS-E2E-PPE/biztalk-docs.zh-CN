---
title: "与 Visual Studio 的 MSBUILD 集成 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aedcabf7-b2cf-482a-9ade-7311e104bff9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4a639945881625dd697798080c913ec0e5e3a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="msbuild-integration-with-visual-studio"></a>与 Visual Studio 的 MSBUILD 集成
Visual Studio 使用 MSBUILD 项目文件格式存储有关管理项目（包括 BizTalk 项目）的生成信息。 通过 Visual Studio 添加和生成的项目设置将反映在为每个项目生成的 .btproj 文件中。 Visual Studio 使用 MSBUILD 的托管实例来生成 BizTalk 项目，即 BizTalk 项目可以在 Visual Studio 或从命令行生成，将具有相同的结果。  
  
 有关 MSBUILD 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)。  
  
 以下过程显示如何使用 MSBUILD 从命令行生成示例 BizTalk 项目。  
  
## <a name="to-build-a-biztalk-project-from-a-command-line"></a>从命令行生成 BizTalk 项目  
  
1.  启动**Visual Studio 命令提示**。  
  
2.  切换到项目目录，然后运行 MSBUILD 命令以生成 BizTalk 解决方案。  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!NOTE]
    >  解决方案可能包含 BizTalk 和非 BizTalk 项目，如 C# 类库。