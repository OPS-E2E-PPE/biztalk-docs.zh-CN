---
title: 安装 BizTalk 适配器包 2016年 |Microsoft Docs
description: 在无提示模式下安装 BAP 2016，32 位与 64 位的典型或自定义安装
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f3e1717-8063-4460-bfdc-a933cd58a5c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ccbffa606db9f26448ee74198eeb4ec67bee94d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363953"
---
# <a name="install-the-biztalk-adapter-pack-2016"></a>安装 BizTalk 适配器包 2016
安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]以下两种方式：  

-   **在交互模式下**:运行安装程序向导  

-   **在静默模式下**:使用命令行  

> [!IMPORTANT]
> - 必须在其中安装的计算机上具有管理特权[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，不考虑是否要安装使用向导或命令行。  
> - 为确保 all[必备软件](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)安装之前安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。

## <a name="typical-vs-custom-installation"></a>典型安装与自定义安装  
列出了安装类型，以及每个选项安装的功能：  

- **典型**并**完成**选项与关联的数据提供程序安装所有适配器。 没有选择特定的适配器的安装的选项。  

- **自定义**选项与关联的数据提供程序将安装一个或多个适配器。 你可以选择要安装的适配器。 如果您选择安装数据提供程序，还必须安装相应的适配器。 但是，你可以无需安装相应的数据提供程序安装适配器。 执行此操作通过展开**ADO 提供程序**节点，并选择不想要安装的提供程序。 请参阅**使用安装向导安装**（在本主题中）。  

   例如，如果在安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，还必须安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。 但是，可以安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]而无需安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。  

## <a name="32-bit-and-64-bit-install-scenarios"></a>32 位和 64 位安装方案
 与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可用于： 

- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 设计时 （时生成的操作的 LOB 应用程序的元数据）

- BizTalk Server 管理控制台 （用于创建物理端口） 的设计时

  > [!NOTE]
  >  BizTalk Server 管理控制台作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。  

- BizTalk 运行时 （发送和接收消息时的 LOB 应用程序）

可以为所有这些任务，使用一台计算机，也可以使用不同的计算机。 因为这两[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以及 BizTalk MMC 是 32 位进程，你必须安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]中完成的设计时任务的计算机上。 

### <a name="32-bit-install-scenario"></a>32 位安装方案
每台计算机上安装以下软件。 如果使用一台计算机，则必须在该计算机上安装所有软件。 

1. 安装 32 位 [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]
2. 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。
3. 安装 32 位 LOB 客户端和其他所需的 Dll。  

### <a name="64-bit-install-scenarios"></a>64 位安装方案

|                                                                                                                 为 Visual Studio 设计时                                                                                                                  |                                                                                                                  为 BizTalk MMC 设计时                                                                                                                   |                                                                                                                                                                                                                                                                                                         Biztalk 运行时                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                Visual Studio 设计时和/或 BizTalk MMC 设计时间 + BizTalk 运行时                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 | 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 | **对于 32 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 64 位 LOB 客户端和其他所需的 Dll。 | **对于 32 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 64 位 LOB 客户端和其他所需的 Dll。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 |

> [!NOTE]
>  你想要执行设计时任务的任何计算机上使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC 中，你必须安装 32 位或[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  

## <a name="install-using-the-setup-wizard"></a>使用安装向导进行安装  
安装步骤[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在交互模式下。  

1. 运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**。  

2. 选择**安装 Microsoft BizTalk 适配器**。 在下一步的窗口中，列出了任何缺少的必备程序。 如果缺少任一元素，然后选择缺少的程序，并为您的安装程序安装它。 

   例如，选择**步骤 2:安装 Microsoft BizTalk 适配器包**或**步骤 3:安装 Microsoft BizTalk 适配器包 (x64)**。  

   > [!NOTE]
   >  如果您正在安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]虚拟机上安装向导可能会显示一条消息，它检查可用磁盘空间。 如果挂起或只是坐在那里，会出现此消息，则我们建议您**在无提示模式下安装**（在本主题中）。  

3. 在欢迎屏幕上，选择**下一步**。  

4. 接受最终用户许可协议 (EULA)，然后选择**下一步**。  

5. 在中**选择安装类型**:  

   -   若要安装的最常见的功能，请选择**典型**。  

   -   若要选择你想要安装的适配器，请选择**自定义**，然后继续下一步。  

   -   若要安装所有功能，请选择**完成**。  

       > [!IMPORTANT]
       >  若要安装用于与你的企业应用程序中，选择适配器**自定义**安装。  

6. **所需**仅在您选择自定义安装。 如果选择了**典型**或**完成**安装，然后跳过此步骤中，并转到步骤 7。  

    1.  在中**自定义安装**，展开**基适配器**若要查看可用的适配器。  

    2.  对于不希望适配器，选择适配器旁的图标，然后选择**整个功能将不可**。  

    3.  展开**ADO 提供程序**，然后选择不想要安装的提供程序。  

    4.  选择“**下一步**”。  

7. 选择“安装”。  

8. 在中**客户体验改善计划**，可以选择进行注册。 如果你注册，可以与 Microsoft 共享的以下数据：  

   - 与正在其安装的计算机硬件相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  

   - 与将用于企业应用程序版本相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  

     [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)提供了详细信息。  

     选择 **确定**。 

   > [!NOTE]
   >  通过在从修复模式下运行安装程序可以随时更改此设置**程序**。  

9. 选择“完成”。  

<a name="BKMK_SilentInst"></a>   
## <a name="install-in-silent-mode"></a>在无提示模式下安装  
 使用**msiexec**命令执行无提示安装。 作为 msiexec 命令的一部分，输入你想要安装的各个组件。 下表列出了每个组件中的值[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 使用这些值来安装 （或删除） 特定的组件。 若要安装 （或删除） 多个组件，可以使用逗号分隔这些值的组合。  


|                                    组件名称                                    |                                                                命令行属性的相应值                                                                 |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        |                                                                                   DbFeature                                                                                    |
| [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] |                                                                                OracleEBSFeature                                                                                |
|           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |                                                                             SapBaseAdapterFeature                                                                              |
|        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |                                                                            SiebelBaseAdapterFeature                                                                            |
|            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |                                                                                   SqlFeature                                                                                   |
|        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |     SapAdoFeature<br /><br /> **请注意**:必须提供此值，仅当你安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]还。      |
|     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | SiebelAdoFeature<br /><br /> **请注意**:必须提供此值，仅当你安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]还。 |
|                                    所有组件                                    |                                                                                      ALL                                                                                       |

> [!IMPORTANT]
>  功能名称不区分大小写。  

 以下步骤显示如何完成的无提示安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]不同组件。  

### <a name="silent-mode-steps"></a>无提示模式下的步骤

1. 打开命令提示符，并转到[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]根中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。  

2. 运行以下命令，根据你想要安装：  

   > [!NOTE]
   >  若要执行无提示安装的基于 x64 的平台上，替换`AdaptersSetup.msi`与`AdaptersSetup64.msi`以下命令中。  

   - 若要执行的完整安装，安装所有适配器包括.NET Framework 数据提供程序，请键入：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
     ```  

   - 若要仅安装[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
     ```  

   - 若要仅安装[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
     ```  

   - 若要仅安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
     ```  

   - 若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]连同[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
     ```  

   - 若要仅安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
     ```  

   - 若要安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]连同[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
     ```  

   - 若要仅安装[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
     ```  

   - 若要安装所有基适配器，请键入：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
     ```  

   - 若要安装两个.NET Framework 数据提供程序，请键入：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
     ```  

   - 任何类型的用逗号分隔的组件的自定义安装。 例如，若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]与[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，和[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
     ```  

   - 您还可以选择无提示安装的一部分注册 CEIP。 键入：  

     ```  
     msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
     ```  

      默认情况下，选项为 false。 

     > [!IMPORTANT]
     >  安装时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]评估版在静默模式下，CEIP 的默认选项为 true。  

     有关详细信息**msiexec**命令中，键入`msiexec`上的命令行和按`ENTER`。 或转至[ http://go.microsoft.com/fwlink/p/?LinkId=103199 ](http://go.microsoft.com/fwlink/p/?LinkId=103199)。

## <a name="known-install-issue"></a>已知的安装问题
有关与安装相关的问题的完整列表，请参阅**故障排除**每个适配器主题。  

**在 64 位计算机上的运行安装程序可能会访问架构文件时引发错误**  

[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]访问 Microsoft.Adapters 时安装程序将引发错误。*\<AdapterName\>*_schema.xml 文件，但继续进行安装适配器。  

**原因**  

如果 32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装在同一计算机上同时使用的目标架构文件是相同。 因此，32 位安装的文件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可能正在由 IIS 使用 64 位安装程序会尝试对其进行访问时。  

**解决方法**  

手动复制 Microsoft.Adapters。 *\<AdapterName\>*_schema.xml 文件从*C:\Program Files\Microsoft BizTalk 适配器包 (x64) \IIS 架构*到*C:\Windows\System32\inetsrv\config\schema*。 

## <a name="next-step"></a>下一步
[安装后步骤](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)