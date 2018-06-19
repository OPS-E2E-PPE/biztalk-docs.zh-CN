---
title: 如何更新运行时计算机 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 576a7065-04b6-436c-acf9-28c8d6e40107
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca8edb4da6b59c33f87100ee3669bb2472d4350c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010894"
---
# <a name="how-to-update-the-runtime-computers"></a>如何更新运行时计算机
目标系统[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用配置运行时计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导在生产环境中运行的生产 BizTalk 组的一部分。 在灾难恢复环境中还原生产 BizTalk 组时，必须在每个更新设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机，因此它指向灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例时它尝试连接到已还原生产 BizTalk 组。 在目标系统中还原的 BizTalk 组后，使用以下过程更新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机。  
  
### <a name="to-update-the-biztalk-server-runtime-computers"></a>若要更新 BizTalk Server 运行时计算机  
  
1.  将编辑的 SampleUpdateInfo.xml 文件复制到 files\microsoft BizTalk 的每个 32 位服务器上的 BizTalk Server\Schema\Restore 目录或 BizTalk 每个 64 位上的 \Program Files (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore 目录在目标系统中的服务器。  
  
2.  在每个 BizTalk 服务器上，打开命令提示符。 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
    > [!NOTE]  
    >  在 64 位计算机上必须打开 64 位命令提示符。  
  
3.  在命令提示符处，导航到 files\microsoft BizTalk Server\Schema\Restore （在 32 位计算机） 上或 （在 64 位计算机） 上的 \Program 文件 (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore 并键入以下命令：  
  
    ```  
    cscript UpdateRegistry.vbs SampleUpdateInfo.xml  
    ```  
  
4.  启用并在目标系统中重新启动所有 BizTalk 主机实例和 BizTalk 服务器上的所有其他 BizTalk 服务。  
  
5.  在目标系统中每个 BizTalk 服务器上重新启动 WMI。 单击**启动**，单击**运行**，类型**services.msc**，然后单击**确定**。 在**服务**MMC 管理单元中，右键单击**Windows Management Instrumentation**和选择**重新启动**。  
  
6.  每个 BizTalk 服务器上，打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**，然后选择**删除**。  
  
7.  右键单击**BizTalk Server 2010 管理**，选择**连接到现有组**、 选择的 SQL Server 数据库实例和数据库对应的 BizTalk 管理数据库的名称BizTalk 组，然后单击**确定**。  
  
    > [!NOTE]  
    >  在更新后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机，你可能还需要更新**SSO 服务器名称**中所示**组属性**对话框中提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 若要更新**SSO 服务器名称**，启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，单击以展开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理，右键单击**BizTalk 组**节点，然后选择**属性**以显示**常规**选项卡[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 然后，在**SSO 服务器名称**文本框中，输入将使用此计算机来访问适配器的配置信息，然后单击企业单一登录服务器名称**确定**。 这是用于连接到 SSO 数据库的 SSO 服务器的名称。  
  
8.  重新启动每个 BizTalk 运行时服务器上的以下 Windows 服务：  
  
    -   企业 SSO 服务  
  
    -   规则引擎更新服务  
  
    -   BizTalk 主机实例  
  
## <a name="see-also"></a>另请参阅  
 [恢复运行时计算机](../technical-guides/recovering-the-runtime-computers.md)