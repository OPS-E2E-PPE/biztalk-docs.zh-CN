---
title: 管理参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.party
helpviewer_keywords:
- Administration Console [BizTalk Server], parties
- managing [parties]
- managing [parties], about managing parties
- parties, managing
ms.assetid: 96d2bcb3-1e38-4dad-a0d6-e5913ba531e7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6f4fb5f56199e694b721acc4af68739275b3cdb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000342"
---
# <a name="managing-parties"></a>管理参与方
使用**参与方**节点，您可以设置业务合作伙伴 （参与方） 或内部部门 （业务配置文件） 与其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案进行交互。 有关详细信息，请参阅[贸易合作伙伴](../core/trading-partners-and-business-profiles.md)。  

您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台创建和配置参与方。 在 BizTalk Server 中创建参与方后，您可能希望使用业务流程与参与方进行交互。 参与方通过角色与业务流程进行交互。 例如，业务流程中可能具有发运方角色。 发运方具有一个或多个关联的参与方。 当业务流程需要确定要使用费用最低的送货公司来发运货物时，则可比较发运方角色中各个参与方的价格。  

 必须登记参与方以将其与特定角色相关联。 通过登记参与方，业务流程可以与该参与方进行交互。 请参阅[如何登记或取消登记角色参与方](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)。

## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  

## <a name="create-or-edit-a-party"></a>创建或编辑参与方

1. 打开 **“BizTalk Server 管理”**。  展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，右键单击**方**，选择**新建**，然后选择**方**。  

2. 上**常规**页上，执行以下操作：  


   |                                                使用此选项                                                 |                                                                                                                                                                                                                                                                      执行的操作                                                                                                                                                                                                                                                                       |
   |---------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                                **名称**                                                 |                                                                                                                                                                                                                                                                  输入参与方名称。                                                                                                                                                                                                                                                                  |
   | **本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息** | 选中此复选框以指定该参与方代表托管 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的同一个贸易合作伙伴。 **重要说明：** 对于双方 TPM 解决方案，它使用开箱管道附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，必须选择至少一个参与方此复选框。 **注意：** 如果清除此复选框，将创建为此参与方协议时禁用某些属性。 |
   |                                **其他属性 – 名称/值**                                 |                                                                                                                                                输入一个名称/值对以存储有关参与方的任何信息。 可以根据需要添加任意数量的名称/值对。 **请注意**： 名称 / 值对不能由 BizTalk Server 进行任何处理; 此数据是为了仅提供信息。                                                                                                                                                 |
   |                                               **删除**                                                |                                                                                                                                                                                                                                                    选择此项可删除所选的名称-值对。                                                                                                                                                                                                                                                     |


3. 上**发送端口**页上，执行以下操作。  

   > [!NOTE]
   >  在 BizTalk Server 发送端口关联在协议级别完成。 **发送端口**页如的参与方属性一部分仅仅是用于向后兼容性。 每当您将发送端口与协议相关联时，发送端口设置也会传播到参与方设置，您同时会在此页面上看到发送端口关联。 但是，反之则不然。 不能将发送端口与参与方关联，然后使该发送端口自动作为协议设置的一部分使用。  

   |       使用此选项        |                                      执行的操作                                       |
   |-----------------------|---------------------------------------------------------------------------------------|
   | **发送端口-名称** |          从下拉列表中选择要绑定到此参与方的发送端口。           |
   | **发送端口-URI**  |                            显示发送端口地址。                            |
   |      **删除**       |                选择此选项可以从该参与方中删除所选的发送端口。                |
   |    **属性**     | 选择此项可显示**发送端口属性**所选的发送端口对话框。 |


4. 上**证书**页上，执行以下操作：  


   |        使用此选项        |                                                                                                                                                 执行的操作                                                                                                                                                 |
   |------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       **“浏览”**       |                                                选择要显示**选择证书**对话框中，在从本地计算机或其他人证书存储，应用到消息传输到参与方选择签名证书。                                                 |
   |    **公用名**     |                                                                                                                            显示所选证书的说明。                                                                                                                             |
   |     **指纹**     | 显示用于参与方解析和签名验证的私钥证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字 （从 0 到 9 的数字） 或为从 A 到 F 的字母。 |
   | **删除证书** |                                                                                                                                选择此项可删除所显示的证书。                                                                                                                                 |


5. 选择**Apply**以接受这些属性，或选择**确定**即可完成配置设置。 以上任一操作均会验证设置  

### <a name="update-an-existing-party"></a>更新现有参与方
参与方登记到角色并将其绑定端口后，您可以：  

- 编辑参与方的名称和说明  
- 编辑参与方的证书  
- 指定参与方是否用于组织托管 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]

1. 在中**BizTalk Server 管理**，然后选择**方**。

2. 在中**参与方和业务配置文件**窗格中，右键单击你想要查看或编辑的参与方，然后选择**属性**。  

3. 查看或编辑的属性。 

4. 选择**Apply**以接受这些属性，或选择**确定**即可完成配置设置。 以上任一操作验证设置。  

## <a name="delete-a-party"></a>删除参与方
删除使用该参与方[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

> [!IMPORTANT]
>  您只能删除未在角色中登记的参与方。 在删除参与方之前，必须首先从该参与方所登记的任何角色中取消登记。 请参阅[如何登记或取消登记角色参与方](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)。 

1. 在中**BizTalk Server 管理**，选择**方**，右键单击你想要删除，然后选择参与的方**删除**。  

2.  在中**确认删除参与方**对话框中，选择**是**以删除该参与方。  

## <a name="search-for-a-party"></a>搜索参与方
如果有大量的创建的参与方，则可以使用**搜索**选项以显示你想要查看的参与方。  

1. 在中**BizTalk Server 管理**，选择**方**。

2. 在中**参与方和业务配置文件**窗格中，顶部附近的右上角中输入的搜索字符串**搜索参与方**文本框，并选择搜索图标。 你还可按 Enter 键开始搜索。  

    使用搜索选项时，你必须注意以下几点：  

   - 搜索字符串不区分大小写

   - 您可以搜索的文本中的名称 （子字符串搜索）。 例如，如果搜索“ar”，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台将显示以该搜索字符串开头的参与方（如 Artist）或名称中包含该搜索字符串的参与方（如 Party1）。  

   - 搜索操作仅限于参与方名称。  

3. 若要清除搜索结果，请选择搜索文本框旁边的红色 x。  

## <a name="see-also"></a>请参阅  
 [管理角色链接](../core/managing-role-links.md)   
 [如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
 [管理 EDI 和 AS2 解决方案](../core/managing-edi-and-as2-solutions.md)