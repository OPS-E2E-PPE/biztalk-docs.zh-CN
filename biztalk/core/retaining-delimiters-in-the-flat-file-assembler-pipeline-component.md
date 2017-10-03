---
title: "保留在平面文件汇编管道组件的分隔符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: adc27561-9996-49a9-b715-e313b9148506
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9d10879adfbe0ca0c68376faa48d9976fc19599
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a>保留平面文件组装器管道组件中的分隔符
如果在经过使用平面文件组装器的自定义管道的消息中缺少某些记录，则根据输入文件中缺少记录的位置，这些记录的分隔符不一定出现在平面文件输出中。  
  
 若要确保该平面文件保留某些分隔符，您可以使用映射和自定义脚本，确保在特定输入记录在消息中不存在时创建一条“空”记录。 为此，您必须确保平面文件组装器的文档架构中可能的空节点设置了如下属性：  
  
|属性|设置|  
|--------------|-------------|  
|为空数据保留分隔符|是|  
|禁止显示尾随分隔符|是|  
|生成空节点（对根节点进行这一设置）|True|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a>创建将创建“空”记录的映射  
  
1.  向 BizTalk 项目添加新映射。  
  
2.  将平面文件组装器使用的文档架构指定为映射源和映射目标架构。  
  
3.  将不为空的源字段映射到相应的目标字段。  
  
4.  对于可能为空的那些字段，使用自定义脚本来检查源字段是否为空并返回空字符串（而非 Nil）。 使用如下脚本：  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  您必须创建对于您映射的每个可能的空字段都具有唯一函数名的脚本。 例如，如果你有可能为空的三个字段，你可能有函数名为`ValOrEmpty1`， `ValOrEmpty2`， `ValOrEmpty3`。  
  
5.  使用 BizTalk Server 管理控制台，将配置发送端口的自定义管道和平面文件汇编组件以使用为出站映射的映射。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置为发送端口的出站映射](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [平面文件汇编管道组件](../core/flat-file-assembler-pipeline-component.md)