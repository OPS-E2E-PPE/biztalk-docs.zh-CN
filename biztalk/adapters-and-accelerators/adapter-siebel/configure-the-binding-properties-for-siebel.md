---
title: 配置用于 Siebel 的绑定属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
- how to, specify binding properties at design time
- how to, specify binding properties at run time
ms.assetid: 063e9507-8172-4fb0-8b9f-2f95e8a82f21
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e09f3ce0f5e21c6ac1df6bb7c361674629fa4d36
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992352"
---
# <a name="configure-the-binding-properties-for-siebel"></a>配置用于 Siebel 的绑定属性
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]显示，您可以控制某些行为特征的多个绑定属性。 本部分提供有关从 Visual Studio （设计时） 和设置的绑定属性的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台 （运行时间）。 在设计时，必须指定要为特定的操作生成架构的绑定属性。 在运行时，必须为发送端口将消息发送到 Siebel 系统的一部分指定的绑定属性。  

 有关绑定属性的信息，其中包括一系列的绑定属性[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  

## <a name="enter-the-binding-properties-at-design-time"></a>在设计时输入的绑定属性  
 对于设计时，你必须指定的绑定属性从[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]对话框。  

#### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a>输入使用适配器服务外接程序使用的绑定属性  

1.  右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。  

2.  在中**添加生成的项**对话框框中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  

3.  若要启动**使用适配器服务**对话框中，单击**添加**。  

4.  在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.  

5.  在中**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  

6.  单击“确定” 。  

#### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a>输入绑定属性使用添加适配器元数据向导  

1. 右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  

4. 在添加适配器向导中，选择**Wcf-siebel**。 选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已配置 BizTalk 中的 WCF Siebel 端口，选择从端口**端口**列表。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.  

7. 在中**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  

   > [!NOTE]
   >  如果选择现有的 WCF Siebel 发送端口，则不需要指定绑定属性。 绑定属性是从发送端口配置中选取。 但是，您可以选择指定如果任何，则需要在设计时的绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定的发送端口配置中的绑定属性的值将适用。  

8. 单击“确定” 。  

## <a name="enter-binding-properties-at-run-time"></a>在运行时输入绑定属性  
 对于运行时中，你必须指定的绑定属性作为 WCF 自定义或中的 WCF Siebel 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

#### <a name="enter-binding-properties-for-the-wcf-custom-port"></a>输入 WCF 自定义端口绑定属性  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**. 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在中**端口属性**对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

4. 在中**Wcf-custom 传输属性**对话框中，单击**绑定**选项卡。  

5. 从**绑定类型**下拉列表中，选择**siebelBinding**。  

6. 在中**配置**框中，指定不同的绑定属性的值，然后单击**确定**。  

#### <a name="enter-binding-properties-for-the-wcf-siebel-port"></a>输入 WCF Siebel 端口绑定属性  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 添加到 WCF 的 Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**. 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在中**端口属性**对话框中，从**类型**下拉列表中，选择你前面，添加的 Wcf-siebel 端口，然后单击**配置**。  

5. 在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。  

6. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
[若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)