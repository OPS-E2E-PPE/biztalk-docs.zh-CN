---
title: "使用绑定文件导入或导出 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9a2a82a-f8d4-4ec2-b8c1-be6cda3f993a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3707726eb9e8e77e0536f36700fe098d83ad414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-binding-files-to-import-or-export"></a>使用绑定文件导入或导出

从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，你可以导出并导入绑定文件在**方**和**协议**级别。 对于早期 BizTalk 版本，你导出应用程序级别中所述： 

* [如何导出 EDI AS2 解决方案的绑定](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [如何导入绑定 EDI AS2 解决方案](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

本主题说明如何导入和导出方、 自己的配置文件、 协议、 回退设置，和详细使用[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]和 BTSTask。 

## <a name="overview"></a>概述

一些导入和导出功能包括：

* 从 XML 绑定文件导入方、 业务配置文件和协议
* 将参与方、 业务配置文件、 协议和 EDI 回退设置导出到 XML 绑定文件
* 在导入绑定文件，你可以选择不导入的参与方或回退设置
* 在导入在方级别，将导入方和绑定文件中的协议
* 将特定方导出到相同的绑定文件，并选择还导出这些方与关联的所有协议
* 应用程序导入绑定向导允许你选择要导入的跟踪设置，或排除方。
* BTSTask 包括`ImportParties`和`ExportParties`命令 

## <a name="prerequisites"></a>先决条件

* 你必须是的成员的帐户登录 * * BizTalk Server 管理员 * * 组。 请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  

* 你必须添加对引用**BizTalk EDI 应用程序**从 BizTalk 应用程序将用作 EDI 应用程序。 请参阅[后配置步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)。

## <a name="import-or-export-all-the-trading-partners"></a>导入或导出所有贸易合作伙伴
1. 打开 **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** ，展开的 BizTalk 组。
2. 右键单击**方**，然后选择**导出**。 

    在导出时**方**-级别时，要导出所有贸易合作伙伴。 这还将导出所有内容使用贸易合作伙伴，包括业务配置文件和到 XML 文件的协议。 

3. 右键单击**方**，选择**导入**，并选择绑定的 XML 文件。 

      选择**排除方**，或**排除 EDI 回退设置**以便它们不会导入。 否则，绑定文件中的所有内容导入，包括贸易合作伙伴、 业务配置文件和协议。     

### <a name="btstask-example"></a>BTSTask 示例

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

请参阅[ImportParties 命令](../core/importparties-command.md)。

    
## <a name="export-individual-partners"></a>导出各个合作伙伴
1. 在 **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** ，选择**方**。
2. 在**方和业务配置文件**窗格中，右键单击一个参与方，然后选择**导出**。

    在导出特定方时，你可以选择要导出所有各方，并由该方使用的所有协议。 你可以取消选中**导出所选的方和中所选的参与方的所有协议**若要仅导出你选择的当事方。

3. 选择“确定”。 

> [!TIP]
> 在**方和业务配置文件**窗格中，你还可以使用**CTRL**和**Shift**键以选择多个方列表中。 所有参与方，选择将导出到相同的绑定文件。

### <a name="btstask-example"></a>BTSTask 示例

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

请参阅[ExportParties 命令](../core/exportparties-command.md)。


## <a name="import-application-binding-file"></a>导入应用程序绑定文件

在应用程序级别，你可以与 EDI 和 AS2 方导绑定文件。 

1. 在 **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** ，展开**应用程序**
2. 右键单击你的应用程序，然后选择**导入**。
3. **导入跟踪设置**和**排除方**选项才可用。 使用这些选项，你可以选择要导入任何现有的跟踪设置，或排除所有绑定文件中的 EDI/AS2 参与方。

    | 设置 | 详细信息 |
    |---|---|
    |**导入跟踪设置** | 导入应用程序，例如跟踪消息正文和跟踪事件中不同的项目上启用的跟踪设置。 <br/><br/>默认启用，以确保向后兼容性。 |
    | **排除方**|执行不导入方、 配置文件，以及协议现有文件中。 <br/><br/>默认情况下，以确保向后兼容性已禁用。|

     > [!IMPORTANT] 
     > 全局跟踪设置替代**导入跟踪设置**。 因此如果已禁用跟踪在全局级别，任何不导入设置的跟踪，即使**导入跟踪设置**已选中。
     > 
     > **BizTalk 设置仪表板，组页**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]说明**允许导入的跟踪设置**全局设置。

### <a name="btstask-example"></a>BTSTask 示例

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

请参阅[ImportBindings 命令](../core/importbindings-command.md)。

## <a name="in-this-section"></a>在本节中
若要导入或导出以前 BizTalk 版本上的 EDI 和 AS2 绑定文件，请参阅： 

* [如何导出 EDI AS2 解决方案的绑定](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [如何导入绑定 EDI AS2 解决方案](../core/how-to-import-bindings-for-an-edi-as2-solution.md)
