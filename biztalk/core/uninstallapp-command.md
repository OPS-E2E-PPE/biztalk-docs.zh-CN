---
title: "UninstallApp 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f45c9530-8138-40f1-b279-1428c5a7fbbc
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea94335882ffbcf01b69c450ef4a5eb80ef4fa3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="uninstallapp-command"></a>UninstallApp 命令
该命令从本地计算机中卸载 BizTalk 应用程序，并且将从“控制面板”的“添加或删除程序”中的程序列表中删除该应用程序。 此命令与使用“添加或删除程序”删除应用程序的效果相同。 如果为要删除的应用程序安装了多个 .msi 文件，则所有这些 .msi 文件安装的全部项都将被卸载。  
  
 为此命令指定的应用程序名称必须与显示在“添加或删除程序”中的应用程序名称相匹配。 如果您不确定的应用程序名称，则可以使用**ListPackage**命令以获取它中, 所述[ListPackage 命令](../core/listpackage-command.md)。  
  
> [!IMPORTANT]
>  虽然通过双击 .msi 文件能够卸载应用程序，但建议不要这样做。 因为可以为同一个应用程序安装多个 .msi 文件，如果采用这种方法卸载应用程序，将不能卸载与该应用程序相关联的所有项。  
  
## <a name="usage"></a>用法  
 **BTSTask UninstallApp /ApplicationName:** *值*  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|Description|  
|---------------|--------------|-----------------|  
|**/ ApplicationName** (或**/A**，请参阅备注)|是|要卸载的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。|  
  
## <a name="sample"></a>示例  
 **BTSTask UninstallApp /ApplicationName:MyApplication**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)