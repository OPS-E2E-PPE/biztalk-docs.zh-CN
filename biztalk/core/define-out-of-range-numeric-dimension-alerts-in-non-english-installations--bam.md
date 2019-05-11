---
title: 如何在非英语系统中定义的范围的数值维度警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f1e0373-eadf-4c6d-9a38-a34d847f310f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703c59f83e0a9af01bcddbea1358a56aa825037b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352480"
---
# <a name="how-to-define-out-of-range-numeric-dimension-alerts-in-non-english-installations"></a>如何在非英语系统中定义的范围的数值维度警报
当设置包含在非英语安装上定义的数值范围维度之外的值的条件的警报，必须手动修改字符串的本地化版本的 BAM 定义**超出范围**.  
  
 下表列出了示例的本地化范围外的值。  
  
|语言代码|已本地化的字符串|  
|-------------------|----------------------|  
|CN|超出范围|  
|DE|Außerhalb des gültigen Bereichs|  
|ES|Fuera de rango|  
|FR|hors 会|  
|IT|Fuori intervallo|  
|JA|範囲外|  
|KO|범위를 벗어남|  
|TW|超過範圍|  
  
### <a name="to-define-out-of-range-alerts-in-non-english-installations"></a>若要在非英语系统中定义的范围的警报  
  
1.  导航到包含您的 BAM 定义 xml 文件的文件夹。  
  
2.  使用文本编辑器或 XML 编辑器，打开 BAM 定义文件。  
  
3.  查找数值维度的切片器维度。 例如，如果名为切片器维度**Alerts_NumDim**，则应该查找以下节点：  
  
    ```  
    <SlicerDimension Name="Alerts_NumDim">  
    <Level Name="(Out of Range)" />  
    </SlicerDimension>  
    ```  
  
4.  更改**超出范围**字符串值与相应的本地化字符串。  
  
5.  保存该文件并部署该定义。  
  
## <a name="see-also"></a>请参阅  
 [什么是 BAM 定义架构？](../core/what-is-a-bam-definition-schema.md)   
 [如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)