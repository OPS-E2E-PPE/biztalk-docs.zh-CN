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
# <a name="msbuild-integration-with-visual-studio"></a><span data-ttu-id="f1592-102">与 Visual Studio 的 MSBUILD 集成</span><span class="sxs-lookup"><span data-stu-id="f1592-102">MSBUILD Integration with Visual Studio</span></span>
<span data-ttu-id="f1592-103">Visual Studio 使用 MSBUILD 项目文件格式存储有关管理项目（包括 BizTalk 项目）的生成信息。</span><span class="sxs-lookup"><span data-stu-id="f1592-103">Visual Studio uses the MSBUILD project file format to store build information about managed projects including BizTalk projects.</span></span> <span data-ttu-id="f1592-104">通过 Visual Studio 添加和生成的项目设置将反映在为每个项目生成的 .btproj 文件中。</span><span class="sxs-lookup"><span data-stu-id="f1592-104">Project settings added and changed through Visual Studio are reflected in the .btproj file that is generated for each project.</span></span> <span data-ttu-id="f1592-105">Visual Studio 使用 MSBUILD 的托管实例来生成 BizTalk 项目，即 BizTalk 项目可以在 Visual Studio 或从命令行生成，将具有相同的结果。</span><span class="sxs-lookup"><span data-stu-id="f1592-105">Visual Studio uses a hosted instance of MSBUILD to build BizTalk projects, meaning that a BizTalk project can be built in Visual Studio or from the command line, with identical results.</span></span>  
  
 <span data-ttu-id="f1592-106">有关 MSBUILD 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)。</span><span class="sxs-lookup"><span data-stu-id="f1592-106">For more information on MSBUILD, see [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
 <span data-ttu-id="f1592-107">以下过程显示如何使用 MSBUILD 从命令行生成示例 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="f1592-107">The following procedure shows you how to use MSBUILD to build a sample BizTalk project from command line.</span></span>  
  
## <a name="to-build-a-biztalk-project-from-a-command-line"></a><span data-ttu-id="f1592-108">从命令行生成 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="f1592-108">To build a BizTalk project from a command line</span></span>  
  
1.  <span data-ttu-id="f1592-109">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="f1592-109">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="f1592-110">切换到项目目录，然后运行 MSBUILD 命令以生成 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="f1592-110">Switch to the project directory, and run a MSBUILD command to build the BizTalk solution.</span></span>  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f1592-111">解决方案可能包含 BizTalk 和非 BizTalk 项目，如 C# 类库。</span><span class="sxs-lookup"><span data-stu-id="f1592-111">The solution may contain BizTalk and non-BizTalk projects, such as a C# class library.</span></span>