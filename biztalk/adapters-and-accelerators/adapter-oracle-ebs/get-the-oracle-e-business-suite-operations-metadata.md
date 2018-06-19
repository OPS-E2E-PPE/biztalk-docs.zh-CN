---
title: 获取 Oracle E-business Suite 操作元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 566ae086-183a-47db-8f93-12b5903c85c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1443219f8562caee53547be3f78df15834ddf4b7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963787"
---
# <a name="get-the-oracle-e-business-suite-operations-metadata"></a>获取 Oracle E-business Suite 操作元数据
你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成为选择的 Oracle E-business Suite 项目的架构。 在浏览并搜索你想要调用的项目后，你可以生成这些项目的架构和发送消息，符合架构，到 Oracle E-business Suite。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]当您浏览和搜索操作，因此相同的主题中所述两个组件时所显示实质上是相同的接口。  
  
## <a name="prerequisites"></a>先决条件  
 在检索元数据的目标操作之前，你必须连接到 Oracle E-business Suite。 有关如何连接到 Oracle 数据库使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
## <a name="generating-schema-using-the-consume-adapter-service-add-in"></a>生成架构使用使用适配器服务外接程序  
  
> [!NOTE]
>  你可以选择要在该类别的子树中返回的所有操作的类别节点-例如，你可以选择**并发程序**节点 （以生成架构的 Oracle 应用程序的并发的所有程序） 也可以选择特定的并发程序。 有关节点的详细信息，请参阅元数据的节点 Id。  
  
#### <a name="to-generate-schema-for-oracle-e-business-suite-artifacts"></a>若要为 Oracle E-business Suite 项目生成架构  
  
1.  连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
    > [!IMPORTANT]
    >  若要生成使用执行操作的架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]必须设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。 建立与 Oracle E-business Suite 的连接时，必须设置此绑定属性。  
  
2.  从**选择协定类型**列表中，选择基于是否正在生成架构的入站或出站操作的协定的类型。  
  
3.  单击你想要生成元数据的类别节点。 例如，如果你想要为 Oracle 应用程序中的并发程序生成元数据，请单击**并发程序**。  
  
4.  展开类别节点中，并选择你想要生成元数据节点中的特定项。 例如，若要生成元数据"银行中心"应用程序的并发程序，展开**并发程序**节点，，然后单击**银行 Center**。  
  
5.  在**可用类别和操作**框中，选择你想要调用，然后单击操作**添加**。 中列出了所选的操作**添加类别和操作**框。 例如，要调用"清除 FTP 银行帐户"和"Get_Status"并发程序，单击操作名称，然后单击**添加**。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了所选的操作。  
  
     ![从 Oracle （&#45;） 检索元数据Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/df7de132-9177-4de7-a620-59dbd561efe5.gif "df7de132-9177-4de7-a620-59dbd561efe5")  
  
     如果你想要为多个操作生成架构，可能有一些重复的元素定义之间可能会导致失败编译 BizTalk 项目这些架构。 例如，考虑其中生成操作"Op1"的架构的方案。 "Op1"的架构包含数据类型"CT1"的参数。 为"Op1"生成架构后，你关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]然后重新打开它以生成用于另一操作"Op2"的架构。 假定"Op2"还包含数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译该项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们的建议如下：  
  
    -   中的一次运行生成的所有操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这样可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成只有一个定义的复杂数据类型"CT1"。  
  
    -   如果你想要跨不同运行的生成对多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含唯一的命名空间复杂数据类型"CT1"。  
  
6.  单击 **“确定”**。 架构文件保存带.xsd 扩展名为 BizTalk 项目所在的位置。  
  
    > [!NOTE]
    >  如果你将使用适配器服务外接程序来生成 Oracle 项目上的操作的元数据，默认情况下创建这些文件使用特定的命名约定： 生成的 XSD 文件名具有以下三个部分：  
    >   
    >  -   中提供"OracleEBSBinding"或前缀**文件名前缀**框。  
    > -   中包含的名称**fileNameHint**中生成的 WSDL 批注标记。 对于操作，文件名称提示是相同的操作组。 对于复杂类型，文件名称提示是不带"http://schemas.microsoft.com/OracleEBS/2008/05/"前缀的命名空间。 例如，界面表操作的文件名称提示遵循约定\<InterfaceTables\>+ < app_short_name > + < interface_table_name >。  
    > -   （可选）要确保文件名称是唯一的整数。  
    >   
    >  最后，一 XSD 文件的名称后到达，作为 < file_name_prefix > 时 +\<fileNameHint\>+ n，其中"n"是一个唯一的整数。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含时指定的绑定属性的绑定文件 （XML 文件） 生成某一操作和要调用的操作的 SOAP 操作的架构。 你可以导入中的此绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建连接 URI 的 WCF 自定义端口、 绑定属性和的 SOAP 操作设置。 有关详细信息，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
     你已成功生成 Oracle E-business Suite 项目的元的数据。 元数据可用于将消息发送到 Oracle E-business Suite 执行特定操作。 请参阅[开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)有关如何执行这些操作的详细信息。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>生成 WCF 客户端或 WCF 服务协定使用添加插件的适配器服务引用  
 你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端代码用于出站操作，或者为入站操作的 WCF 服务代码。  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-oracle-e-business-suite-operations"></a>若要生成 WCF 客户端类或服务协定用于 Oracle E-business Suite 操作  
  
1.  在[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择基于你将会执行入站或出站操作的协定的类型。  
  
2.  浏览或搜索的类别 （如接口表中） 或你想要生成 WCF 客户端 （或 WCF 服务协定） 的特定操作。   
    例如，若要浏览查找 AR_ARCHIVE_PURGE_INTERIM 接口表上的操作中**选择类别**框：  
  
    1.  展开根节点 (**/**) 若要查看在其下操作中加以表示为 Oracle E-business Suite 的类别。 相同的接口表可以提供下**基于应用程序的视图**节点以及**基于项目的视图**节点。 在此示例中，生成 WCF 客户端类从**基于应用程序的视图**节点。  
  
    2.  在根节点下展开**基于应用程序的视图**节点以查看 Oracle E-business Suite 中可用的应用程序。  
  
    3.  展开的节点**应收帐款**应用程序，然后展开**接口表**节点。  
  
    4.  单击**AR_ARCHIVE_PURGE_INTERIM**接口表节点，然后在**可用类别和操作**框中，选择你想要生成 WCF 客户端 （或 WCF 服务的操作协定），然后单击**添加**。 中列出了所选的操作**添加类别和操作**框。  
  
         下图显示[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]与选择的 AR_ARCHIVE_PURGE_INTERIM 表的插入，然后选择操作。  
  
         ![生成 WCF 客户端或服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/media/oraebs-adap-add-adap-serv-refs.gif "oraebs_adap_add_adap_serv_refs")  
  
        > [!IMPORTANT]
        >  具体取决于的出站操作 （或类别），您选择，超过一个 WCF 客户端类可能会生成。 有关更多详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
3.  在大多数情况下的默认序列化选项已足够;但是，如果需要你可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
    1.  单击**高级选项**以打开**高级选项**框。  
  
    2.  在**高级选项**下框中**选择生成的代理的选项**，选择所需的选项。 例如，你可以选择是否为 WCF 客户端生成异步方法，或禁用配置文件的生成。  
  
    3.  下**序列化程序**选择应使用的序列化程序。  
  
     下图显示**高级选项**包装盒默认选择 (**自动**选择为所选序列化程序和任何其他选项)。  
  
     ![高级选项框中的默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     你可以在配置的选项**高级选项**使用 ServiceModel 元数据实用工具 (svcutil.exe) 时，框将等效于某些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel 元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
4.  单击 **“确定”**。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将保存的 WCF 客户端类 （或 WCF 服务接口） 和帮助器代码的操作和你选择了你的项目目录中的类别。 默认情况下，也保存配置文件。 为入站和出站操作; 生成略有不同的文件有关详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
 你可以选择中列出的任何节点**可用类别和操作**框。 如果你选择的类别节点，则该节点及其子节点下可执行的操作的所有将被选中。 例如，若要生成的所有操作 AR_ARCHIVE_PURGE_INTERIM 表中加以表示的 WCF 客户端，你可以选择**AR_ARCHIVE_PURGE_INTERIM**节点。  
  
## <a name="see-also"></a>另请参阅  
 [浏览、 搜索和用于 Oracle E-business Suite 操作获取元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)