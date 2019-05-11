---
title: 保留平面文件组装器管道组件中的分隔符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc27561-9996-49a9-b715-e313b9148506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f975f04bb18dca5cc8e311fdb21d7b44caf01d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322134"
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a>保留平面文件组装器管道组件中的分隔符
如果消息经过使用平面文件组装器的自定义管道中有缺失的记录，这些记录的分隔符可能或可能不会显示在平面文件输出，具体取决于在其中输入文件中的记录将会丢失。  
  
 以确保该平面文件保留某些分隔符，则可以使用映射和自定义脚本以确保在特定输入的记录不存在消息中时，将创建"空"记录。 为实现此目的，你必须确保平面文件组装器的文档架构中的可能的空节点已按所示设置以下属性：  
  
|属性|设置|  
|--------------|-------------|  
|为空数据保留分隔符|是|  
|取消尾部分隔符|否|  
|生成空节点 （这在设置的根节点）|True|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a>若要创建映射，将创建一个"空"记录  
  
1.  向 BizTalk 项目添加新的映射。  
  
2.  指定使用平面文件组装器作为映射源和映射目标架构的文档架构。  
  
3.  将不为空到相应的目标字段的源字段映射。  
  
4.  这些字段可能为空的使用自定义脚本来检查源字段是否为空并返回空字符串 （而非 Nil)。 使用脚本如下所示：  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  替换为您映射的每个可能的空字段的唯一函数名称，必须创建一个脚本。 例如，如果有三个字段可能为空的则可能必须名为的函数`ValOrEmpty1`， `ValOrEmpty2`， `ValOrEmpty3`。  
  
5.  使用 BizTalk Server 管理控制台中，使用自定义管道和平面文件组装器组件以将映射用作出站映射配置发送端口。  
  
## <a name="see-also"></a>请参阅  
 [如何配置发送端口的出站映射](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [平面文件汇编程序管道组件](../core/flat-file-assembler-pipeline-component.md)