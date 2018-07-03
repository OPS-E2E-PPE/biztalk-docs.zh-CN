---
title: 用于 Oracle 数据库配置的绑定属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at run time
- binding properties, specifying at design time
ms.assetid: c59a1b5c-b52b-4161-82de-c4d89bfce5c7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96922feab7c343893bfaa04ccbccd7c7e2f6a743
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981078"
---
# <a name="configure-the-binding-properties-for-oracle-database"></a>用于 Oracle 数据库配置的绑定属性
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]显示，您可以控制某些行为特征的多个绑定属性。 本部分提供有关从 Visual Studio 和 BizTalk Server 管理控制台设置的绑定属性的信息。 从 Visual Studio 中，必须在生成针对特定操作的架构时指定的绑定属性。 从 BizTalk Server 必须绑定属性指定为一部分发送或接收端口来发送或从 Oracle 数据库接收消息。  

 有关绑定属性的信息，其中包括一系列的绑定属性[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  

## <a name="specifying-binding-properties-from-visual-studio"></a>指定从 Visual Studio 绑定属性  
 必须从 Visual Studio 中，指定使用的凭据[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a>若要指定使用适配器服务外接程序使用的绑定属性  

1.  右键单击 BizTalk 项目，然后选择**添加生成的项**。  

2.  在中**添加生成的项**对话框框中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  

3.  若要启动**使用适配器服务**对话框中，单击**添加**。  

4.  在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**oracleDBBinding**，然后单击**配置**.  

5.  在中**配置适配器**对话框中，单击**绑定属性**选项卡上，指定不同的绑定属性。  

6.  单击“确定” 。  

#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a>若要指定绑定属性使用添加适配器元数据向导  

1. 右键单击 BizTalk 项目，然后选择**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 添加适配器元数据向导将打开。  

4. 在添加适配器元数据向导中，选择**Wcf-oracledb**。 选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已在 BizTalk 中配置的 Wcf-oracledb 端口，选择从端口**端口**列表。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**oracleDBBinding**，然后单击**配置**.  

7. 在中**配置适配器**对话框中，单击**绑定属性**选项卡，并指定的绑定值，如果有，生成架构之前所需的。 有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  

   > [!NOTE]
   >  如果选择现有 Wcf-oracledb 发送端口，则不需要指定绑定属性。 绑定属性是从发送端口配置中选取。 但是，您可以选择指定如果任何，则需要在设计时的绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定的发送端口配置中的绑定属性的值将适用。  

8. 单击“确定” 。  

## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a>指定 BizTalk Server 管理控制台中的绑定属性  
 从 BizTalk Server 管理控制台中，必须为 WCF 自定义或 Wcf-oracledb 端口配置的一部分指定的绑定属性。  

#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a>若要指定的 WCF 自定义端口绑定属性  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

4. 在中**Wcf-custom 传输属性**对话框中，单击**绑定**选项卡。  

5. 从**绑定类型**下拉列表中，选择**oracleDBBinding**。  

6. 在中**配置**框中，指定不同的绑定属性的值，然后单击**确定**。  

#### <a name="to-specify-binding-properties-for-the-wcf-oracledb-port"></a>若要指定 Wcf-oracledb 端口的绑定属性  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 将 Wcf-oracledb 适配器添加到 BizTalk Server 管理控制台。 有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加 Wcf-oracledb 适配器，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

5. 在传输属性对话框中，单击**绑定**选项卡，并指定绑定属性的值。  

   > [!NOTE]
   >  绑定属性将显示根据配置发送端口或接收端口。 例如，与通知相关的绑定属性不可用时配置的发送端口，因为通知的入站的操作并且需要进行接收端口配置。  

## <a name="see-also"></a>请参阅  
[若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)