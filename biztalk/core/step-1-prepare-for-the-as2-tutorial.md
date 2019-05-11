---
title: 第 1 步：AS2 教程的准备工作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3421c33b-0ccd-4e9d-b1c3-b161278e4d98
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e355aef2ee6a86ce2d8517bc8664ddea00b3d8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392836"
---
# <a name="step-1-prepare-for-the-as2-tutorial"></a>第 1 步：AS2 教程的准备工作
![步骤 1 部分，共 11](../core/media/tut-step1-of-11.gif "Tut_Step1_of_11")  
  
 AS2 教程在单台计算机上运行。 若要准备本教程，必须安装和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中所述[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)部分。 本主题中所述，还必须添加对 BizTalk Server EDI 应用程序的引用。 AS2 教程所需的文件位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial 文件夹。  
  
> [!NOTE]
>  若要运行本教程，需要在进程内主机实例和独立主机实例使用相同的登录帐户。  
  
> [!NOTE]
>  若要运行本教程来说，本教程中使用的 BizTalk Server 主机必须标记为 32 位。  
  
> [!NOTE]
>  本教程中工作，必须使用 IIS 7.0 或 IIS 7.5 的平台上运行和应用程序池启用 32 位应用程序设置必须设置为 True。  
  
 AS2 教程文件夹包括三个文件夹的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将向其中写入测试输出文件 (EDI 负载、 997 和 MDN)。 这些文件夹已创建，但必须设置为两个 997 和 MDN 文件夹 （请参阅下面的过程） 的安全权限。  
  
 文件夹和教程所需的文件如下所示：  
  
|Folder\File|用途|  
|------------------|-------------|  
|\\_997ToFabrikam|此空文件夹将接收 EDI 处理之后返回的 997 确认消息。 此文件夹模拟应用程序发起的 Fabrikam 参与方的 EDI 消息。|  
|\\_EDIXMLToContoso|BizTalk Server 处理 EDI 消息后，此空文件夹将接收 XML 负载文件。 此文件夹模拟 EDI 负载的最终目标的业务线应用程序。|  
|\\_MDNToFabrikam|此空文件夹将接收 AS2 处理之后从 BizTalk Server 返回的 MDN 消息。 此文件夹模拟 Fabrikam 参与方的应用程序。|  
|\Fabrikam|此文件夹包含将 997 保存到 _997ToFabrikam 文件夹，并将 MDN 保存到 _MDNToFabrikam 文件夹的 Default.aspx 文件。|  
|\Schemas|此文件夹包含的 X12_00401_864.xsd 架构和其他 BizTalk 用于处理 EDI 消息的架构。 该文件夹还包含将生成并部署，以便将架构部署的 Schemas.btproj 项目。|  
|\Sender|此文件夹包含将生成的 Sender.csproj 项目和编译以创建使用 （在中 \AS2 Tutorial 文件夹中） 发送 X12_00401_864.edi 测试消息，并返回 MDN 的 Sender.exe。|  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-set-the-security-permission-for-the-997-and-mdn-folders"></a>若要设置为 997 和 MDN 文件夹的安全权限  
  
1. 在 Windows 资源管理器，转至[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_997ToFabrikam 文件夹。 右键单击\\_997ToFabrikam 文件夹，然后单击**属性**。  
  
2. 单击**安全**选项卡，然后依次**编辑**。 在中**权限**对话框中，单击**添加**。  
  
3. 在中**选择用户、 计算机、 服务帐户或组**对话框中的，在对象名称窗格中，输入`Everyone`，然后单击**确定**。  
  
4. 选择**每个人都**中**组或用户名**框中，单击复选框**编写**(下**允许**列) 中**权限**窗格中，，然后单击**确定**。  
  
5. 单击“确定” 。  
  
6. 重复上述步骤\\_MDNToFabrikam 文件夹。  
  
#### <a name="to-mark-the-biztalk-server-host-as-32-bit"></a>若要将标记为 32 位 BizTalk Server 主机  
  
1. > [!NOTE]
   >  AS2 管道只能在 32 位进程中。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位操作系统，必须执行以下步骤以仅将标记为 32 位主机进程。  
  
    选择**启动**，选择**所有程序**，选择**Microsoft BizTalk Server**，然后选择**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，选择**平台设置**，然后选择**主机**。  
  
3. 在详细信息窗格中，右键单击你想要使用本教程中，然后选择该进程内主机**属性**。  
  
4. 在中**主机属性**对话框中，在**常规**选项卡上，选择**仅限 32 位**，然后单击**确定**。  
  
5. 为独立主机重复步骤 3-4。  
  
   如果在 64 位操作系统上安装 BizTalk Server，还必须设置 IIS 时使用的 32 位 BizTalk 主机进程在 32 位模式下运行。 如何设置 IIS 中的显示[步骤 5:配置贸易合作伙伴网页](../core/step-5-configure-the-trading-partner-web-pages.md)，如 IIS 可以设置 32 位工作进程上每个应用程序池。  
  
#### <a name="to-add-reference-to-the-biztalk-edi-application"></a>若要添加到 BizTalk EDI 应用程序的引用  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**应用程序**节点，右键单击你想要为 EDI，如 BizTalk Application 1 使用的应用程序。 指向**添加**，然后单击引用。  
  
2. 在中**添加应用程序引用**对话框中，选择**BizTalk EDI 应用程序**，然后单击**确定**。  
  
## <a name="next-steps"></a>后续步骤  
 如中所述部署示例 X12 架构[步骤 2:创建和部署示例 X12 架构](../core/step-2-create-and-deploy-the-sample-x12-schema.md)  
  
## <a name="see-also"></a>请参阅  
 [教程 3：AS2 教程](../core/tutorial-3-as2-tutorial.md)