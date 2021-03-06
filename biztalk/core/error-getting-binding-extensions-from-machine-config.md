---
title: 从 machine.config 获取绑定扩展的错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65ab48cf-575b-4db6-984a-880f7e286959
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba98838d56287453b8d0b162dc531dbc3c1cbc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388826"
---
# <a name="error-getting-binding-extensions-from-machineconfig"></a>从 machine.config 获取绑定扩展时出错。
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                从 machine.config 获取绑定扩展时出错。                |
  
## <a name="explanation"></a>解释  
 此错误发生时接收位置或发送端口绑定配置具有用户定义绑定扩展，但 machine.config 文件中未定义。 主要与 Wcf-custom 和 Wcf-customisolated 适配器出现这种情况。  
  
## <a name="user-action"></a>用户操作  
 定义接收位置中使用的绑定扩展或 machine.config 文件中的发送端口。 此外，若要获取自定义行为或绑定元素以使用 Wcf-custom 适配器，请完成以下步骤：  
  
1.  GAC 程序集  
  
2.  修改 machine.config 文件 (位于 **%FrameworkDir%\v4.0.30319\CONFIG**)。  
  
    1.  行为在服务配置编辑器 DLL 加载到 (**svcConfigEditor.exe**)。  
  
    2.  保存到配置**app.config**文件  
  
    3.  复制并粘贴**system.servicemodel** extensions 节在 machine.config 中相似的部分。如果**system.servicemodel**部分不在 machine.config，您必须创建一个。 以下是 machine.config 文件的示例从配置部分：  
  
        ```  
          <system.serviceModel>  
            <extensions>  
              <behaviorExtensions>  
                <add name="BizTalkWcfContractNamespaceTestServiceBehaviorExtension" type="ASB.BizTalk.Samples.BizTalkWcfContractNamespaceTestServiceBehaviorExtension, CustomBizTalkWcfBehaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=7631521c07cf34b4" />  
              </behaviorExtensions>  
            </extensions>  
          </system.serviceModel>  
        ```  
  
> [!NOTE]
>  此外可以将上面的代码添加到 WCF 扩展选项卡。如果扩展需要位于接收端，请参阅 **\<主机名\>属性对话框中，WCF 扩展** 选项卡 （Wcf-custom 或 Wcf-customisolated 适配器接收处理程序） [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 如果扩展插件需要在发送端，请参阅 **\<主机名\>属性对话框中，WCF 扩展**选项卡 （Wcf-custom 适配器发送处理程序） [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
 3. 关闭并重新打开管理控制台。 您应能够看到您在 WCF 自定义适配器的自定义行为，该端口应保持启用状态时启用它。