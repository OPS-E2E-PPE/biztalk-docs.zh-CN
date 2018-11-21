---
title: 使用绑定文件导入或导出 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9a2a82a-f8d4-4ec2-b8c1-be6cda3f993a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af5902812edb528504b2eeac402aad77f647582a
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752869"
---
# <a name="use-binding-files-to-import-or-export"></a>使用绑定文件导入或导出

从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，可以导出和导入绑定文件，在**方**并**协议**级别。 对于以前的 BizTalk 版本，则导出应用程序级别中所述： 

* [如何导出 EDI-AS2 解决方案的绑定](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [如何导入 EDI-AS2 解决方案的绑定](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

本主题介绍如何导入和导出的参与方、 他们的配置文件、 协议、 回退设置，和更多使用[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]和 BTSTask。 

## <a name="overview"></a>概述

一些导入和导出功能包括：

* 从 XML 绑定文件导入参与方、 业务配置文件和协议
* 将参与方、 业务配置文件、 协议和 EDI 回退设置导出到 XML 绑定文件
* 在导入绑定文件，您可以选择导入参与方或后备设置
* 在导入在参与方级别，将导入参与方和绑定文件中的协议
* 将特定参与方导出到相同的绑定文件，并选择还导出这些参与方与关联的所有协议
* 应用程序导入绑定向导允许您选择要导入跟踪设置，或排除参与方。
* BTSTask 包括`ImportParties`和`ExportParties`命令 

## <a name="prerequisites"></a>必要條件

* 您必须是的成员的帐户登录**BizTalk Server Administrators**组。 请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  

* 您必须添加对的引用**BizTalk EDI 应用程序**从将用作 EDI 应用程序的 BizTalk 应用程序。 请参阅[配置后步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)。

## <a name="import-or-export-all-the-trading-partners"></a>导入或导出所有贸易合作伙伴
1. 打开 **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** ，然后展开 BizTalk 组。
2. 右键单击**参与方**，然后选择**导出**。 

    在导出时**参与方**-级别，您要导出所有贸易合作伙伴。 这还将导出所有内容使用的贸易合作伙伴，包括业务配置文件和协议为 XML 文件。 

3. 右键单击**参与方**，选择**导入**，并选择绑定 XML 文件。 

      选择**排除参与方**，或**排除 EDI 回退设置**以便它们不会导入。 否则，该绑定文件中的所有内容导入，包括贸易合作伙伴、 业务配置文件和协议。     

### <a name="btstask-example"></a>BTSTask 示例

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

请参阅[ImportParties 命令](../core/importparties-command.md)。

    
## <a name="export-individual-partners"></a>导出各个合作伙伴
1. 在中 **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** ，选择**方**。
2. 在中**参与方和业务配置文件**窗格中，右键单击参与方，然后选择**导出**。

    在导出特定参与方时，你可以选择要导出所有参与方，并使用该参与方的所有协议。 你可以取消选中**导出选定参与方及其中的所有协议**若要仅导出所选的参与方。

3. 选择“确定”。 

> [!TIP]
> 在中**参与方和业务配置文件**窗格中，您还可以使用**CTRL**并**Shift**键在列表中选择多个参与方。 所有参与方选择导入相同的绑定文件。

### <a name="btstask-example"></a>BTSTask 示例

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

请参阅[ExportParties 命令](../core/exportparties-command.md)。


## <a name="import-application-binding-file"></a>导入应用程序绑定文件

在应用程序级别，您可以使用导入绑定文件 EDI 和 AS2 参与方。 

1. 在中 **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** ，展开**应用程序**
2. 右键单击您的应用程序，然后选择**导入**。
3. **导入跟踪设置**并**排除参与方**选项才可用。 使用这些选项，您可以选择要导入任何现有的跟踪设置，或排除任何 EDI/AS2 参与方绑定文件中。

    | 设置 | 详细信息 |
    |---|---|
    |**导入跟踪设置** | 导入应用程序，如跟踪消息正文和跟踪事件中不同的项目上启用的跟踪设置。 <br/><br/>默认情况下启用，以确保向后兼容性。 |
    | **排除参与方**|执行该文件中的现有未导入参与方、 配置文件和协议。 <br/><br/>若要确保向后兼容性默认情况下禁用。|

   > [!IMPORTANT]
   > 全局跟踪设置将覆盖**导入跟踪设置**。 因此如果已禁用跟踪在全局级别，任何不导入设置的跟踪，即使**导入跟踪设置**检查。
   > 
   > **BizTalk 设置仪表板，组页**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]解释了**允许导入跟踪设置**全局设置。

### <a name="btstask-example"></a>BTSTask 示例

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

请参阅[ImportBindings 命令](../core/importbindings-command.md)。

## <a name="in-this-section"></a>本节内容
若要导入或导出以前的 BizTalk 版本上的 EDI 和 AS2 绑定文件，请参阅： 

* [如何导出 EDI-AS2 解决方案的绑定](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [如何导入 EDI-AS2 解决方案的绑定](../core/how-to-import-bindings-for-an-edi-as2-solution.md)
