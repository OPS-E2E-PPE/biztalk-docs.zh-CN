---
title: 为 Oracle E-business Suite 配置的绑定属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfdca8c8-4434-4a9f-8e2a-970988c2f685
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddb414ae80e7cff6717d232d1734ec8b98cd2006
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217541"
---
# <a name="configure-the-binding-properties-for-oracle-e-business-suite"></a>为 Oracle E-business Suite 配置的绑定属性
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]面，使您能够控制其行为特征一部分的多个绑定属性。 本部分提供有关设置中的绑定属性的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，生成针对特定操作的架构时，必须指定的绑定属性。 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须指定的绑定属性作为一部分发送或接收端口来发送或接收来自 Oracle E-business Suite 的消息。  
  
 有关绑定属性的信息，包括一个绑定的属性列表[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
## <a name="specifying-binding-properties-from-visual-studio"></a>指定 Visual Studio 中的绑定属性  
 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定使用的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a>指定使用适配器服务外接程序中使用的绑定属性  
  
1.  右键单击你的 BizTalk 项目，然后选择**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  
  
3.  若要启动**使用适配器服务**对话框中，单击**添加**。  
  
4.  在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**oracleEBSBinding**，然后单击**配置**.  
  
5.  在**配置适配器**对话框中，单击**绑定属性**选项卡上，然后指定不同的绑定属性。  
  
6.  单击 **“确定”**。  
  
#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a>若要指定绑定属性使用添加适配器元数据向导  
  
1.  右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**添加适配器**。|  
    |**模板**|单击**添加适配器元数据**。|  
  
3.  单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  
  
4.  在[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择**WCF OracleEBS**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  
  
    > [!IMPORTANT]
    >  如果你已有在 BizTalk 中配置 WCF OracleEBS 端口，请从端口列表中选择端口。  
  
5.  单击 **“下一步”**。  
  
6.  在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleEBSBinding**，然后单击**配置**.  
  
7.  单击**绑定属性**选项卡，然后指定的绑定值中，如果有的话，生成架构之前所需的。 有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
    > [!NOTE]
    >  如果你选择的现有 WCF OracleEBS 发送端口，你需要指定的绑定属性。 绑定属性是从发送端口配置中选取。 但是，你可以选择指定所需在设计时，如果任何绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定中发送端口配置的绑定属性的值将适用。  
  
8.  单击 **“确定”**。  
  
## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a>指定将属性绑定从 BizTalk Server 管理控制台  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须作为 WCF 自定义或 WCF OracleEBS 端口配置的一部分指定的绑定属性。  
  
#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a>若要指定的 WCF 自定义端口的绑定属性  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
3.  在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
4.  在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。  
  
5.  从**绑定类型**列表中，选择**oracleEBSBinding**。  
  
6.  在**配置**框中，为不同的绑定属性中，指定值，然后单击**确定**。  
  
#### <a name="to-specify-binding-properties-for-the-wcf-oracleebs-port"></a>若要指定 WCF OracleEBS 端口的绑定属性  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。  
  
3.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
4.  在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF OracleEBS 适配器，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
5.  在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。  
  
    > [!NOTE]
    >  绑定属性显示的配置发送端口或接收端口。 例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。  
  
## <a name="see-also"></a>另请参阅  
 [创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)