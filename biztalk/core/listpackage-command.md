---
title: ListPackage 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be09b76b-429b-4639-89f0-1eadb0c851ce
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c2469a509545dffc80a79a61a5f8f761f5bb724
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970462"
---
# <a name="listpackage-command"></a>ListPackage 命令
列出了生成的.msi 文件中包含的项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="usage"></a>用法  
 **BTSTask ListPackage** [**/包：**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|Description|  
|---------------|--------------|-----------------|  
|**/ 打包**或  **/P**|是|.msi 文件的名称和路径。 示例： C:\MSI\MyApplication.msi。 如果路径中包含空格，则必须放在双引号 （"） 中。|  
  
## <a name="sample"></a>示例  
 **ListPackage /Package:"C:\My MSI Files\MyApplication.msi"**  
  
## <a name="remarks"></a>Remarks  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)