---
title: "ListPackage 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be09b76b-429b-4639-89f0-1eadb0c851ce
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88fca4820dba7c04908e2b756fda0d1d25794a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="listpackage-command"></a>ListPackage 命令
列出的项目中生成的.msi 文件包含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="usage"></a>用法  
 **BTSTask ListPackage** [**/包：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|Description|  
|---------------|--------------|-----------------|  
|**/ 包**或  **/P**|是|.msi 文件的名称和路径。 示例： C:\MSI\MyApplication.msi。 如果路径包含空格，它必须括在双引号 （"） 中。|  
  
## <a name="sample"></a>示例  
 **ListPackage /Package:"C:\My MSI Files\MyApplication.msi"**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)