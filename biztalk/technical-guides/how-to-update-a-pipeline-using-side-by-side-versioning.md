---
title: "如何更新管道使用的并行版本控制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c4e8803128f2232905229de3b5de49994e039ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a>如何更新管道使用的并行版本控制
若要使用的并行版本控制添加一条新管道的简单方法是在发送端口中选择新部署的管道版本或者接收位置。 这将替换为新替换旧的管道。 但是，如果你需要 true 的并行功能用于获取向后兼容性，然后必须创建新的发送端口和接收位置并将其绑定到指定的新管道版本。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a>若要添加管道组件的新版本  
  
1.  在 Visual Studio 中，创建管道组件的新版本，并且对程序集签名。  
  
2.  添加中的管道组件**管道组件**文件夹 (\<*安装文件夹*> \Pipeline 组件)。  
  
3.  将管道组件添加到管道。  
  
4.  生成管道或将部署你的解决方案后, 删除管道组件从**管道组件**文件夹。  
  
5.  将管道组件添加到全局程序集缓存 (GAC) 中。  
  
 完成这些步骤、 编译的管道程序集将引用的管道组件的正确版本和 AppDomain 使用后[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]将在 GAC 中，找到管道组件最新版本，而不是查找上一个管道组件文件夹中的管道组件的版本。  
  
## <a name="see-also"></a>另请参阅  
 [更新使用的并行版本控制](../technical-guides/updating-using-side-by-side-versioning.md)