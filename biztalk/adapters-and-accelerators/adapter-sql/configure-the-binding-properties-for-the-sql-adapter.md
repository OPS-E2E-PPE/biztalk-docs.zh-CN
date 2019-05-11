---
title: 配置 SQL 适配器的绑定属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2edbd90-039a-48b4-a6fc-d825b4957207
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a324672d21b98f88fb23f3ac95a9f4febd77a2c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369981"
---
# <a name="configure-the-binding-properties-for-the-sql-adapter"></a>配置 SQL 适配器的绑定属性
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]显示，您可以控制某些行为特征的多个绑定属性。 本部分提供有关设置中的绑定属性的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]以及从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定要为特定的操作生成架构的绑定属性。 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须指定的绑定属性作为一部分发送或接收端口来发送或接收来自 SQL Server 的消息。  

 有关绑定属性的信息，其中包括一系列的绑定属性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  

## <a name="enter-the-binding-properties-in-visual-studio"></a>在 Visual Studio 中输入的绑定属性  
 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，可以指定使用的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

### <a name="using-consume-adapter-service-add-in"></a>使用使用适配器服务外接程序  

1.  右键单击 BizTalk 项目中，然后依次**添加生成的项**。  

2.  在中**添加生成的项**对话框框中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  

3.  若要启动**使用适配器服务**对话框中，单击**添加**。  

4.  在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**.  

5.  在中**配置适配器**对话框中，单击**绑定属性**选项卡，然后指定不同的绑定属性。  

6.  单击“确定” 。  

### <a name="using-add-adapter-metadata-wizard"></a>使用添加适配器元数据向导  

1. 右键单击 BizTalk 项目，指向**外**，然后单击**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]随即打开。  

4. 在添加适配器向导中，选择**WCF-SQL**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已配置 BizTalk 中的 WCF SQL 端口，选择从端口**端口**列表。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**.  

7. 单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  

   > [!NOTE]
   >  如果选择现有 WCF-SQL 发送端口，则不需要指定绑定属性。 绑定属性是从发送端口配置中选取。 但是，您可以选择指定如果任何，则需要在设计时的绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定的发送端口配置中的绑定属性的值将适用。  

8. 单击“确定” 。  

## <a name="enter-binding-properties-from-the-biztalk-server-administration-console"></a>从 BizTalk Server 管理控制台输入绑定属性  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，可以为 WCF 自定义或 WCF SQL 端口配置的一部分指定的绑定属性。  

### <a name="enter-binding-properties-for-wcf-custom-port"></a>输入 WCF 自定义端口绑定属性  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

4. 在中**Wcf-custom 传输属性**对话框中，单击**绑定**选项卡。  

5. 从**绑定类型**列表中，选择**sqlBinding**。  

6. 在中**配置**框中，指定不同的绑定属性的值，然后单击**确定**。  

### <a name="enter-binding-properties-for-the-wcf-sql-port"></a>输入 WCF SQL 端口绑定属性  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加 WCF SQL 适配器，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

5. 在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。  

   > [!NOTE]
   >  绑定属性将显示根据配置发送端口或接收端口。 例如，与通知相关的绑定属性不可用时配置的发送端口，因为通知的入站的操作并且需要进行接收端口配置。  

6. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)