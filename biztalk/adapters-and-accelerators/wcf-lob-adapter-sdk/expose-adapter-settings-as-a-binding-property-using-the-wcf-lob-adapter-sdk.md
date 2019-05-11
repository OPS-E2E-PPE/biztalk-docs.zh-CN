---
title: 将适配器设置为使用 WCF LOB 适配器 SDK 的绑定属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59728113-917e-4bca-8e1a-609cd6558944
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bae73accfb6e65624f672ce1674b9e0429b6f3da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363632"
---
# <a name="expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk"></a>将适配器设置为使用 WCF LOB 适配器 SDK 的绑定属性
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]使用不同的类来配置连接池、 元数据缓存和其他适配器行为中定义的属性。 本主题介绍作为绑定属性，您就可能会出现这些属性，以便适配器使用者可以通过配置文件设置它们。  
  
### <a name="to-surface-an-adapter-setting-as-an-adapter-binding-property"></a>若要显示为适配器绑定属性的适配器设置  
  
1. 启动 Visual Studio，然后在**文件**菜单，依次指向**新建**，然后单击**项目**。  
  
2. 选择**WCF LOB 适配器**模板，然后提供其他适配器项目信息。  
  
3. 单步执行[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]。 当您到达**适配器属性**页上，添加你想要公开提供的绑定属性**属性名称**，**数据类型**，和**默认值**，然后单击**添加**添加新的适配器属性。  
  
4. 完成[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]。 你的项目应包含由向导提供的新文件。  
  
5. 在 Visual Studio 中，在解决方案资源管理器中打开适配器派生类。 例如，如果适配器项目的名称，"SampleAdapter"可以"SampleAdapter.cs"中找到的派生的适配器类。  
  
6. 删除你想要获取和设置从适配器设置的属性的私有变量。 私有变量由生成[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]。  
  
7. 更新 get/set 方法为读/写从/向适配器设置的值。 以下示例使用适配器属性以允许启用性能计数器。  
  
   ```  
   [System.Configuration.ConfigurationProperty("enablePerfCounters", DefaultValue = false)]  
   public bool EnablePerfCounters  
   {  
       get { return environmentSettings.PerformanceCounters.Enabled;    }  
       set { environmentSettings.PerformanceCounters.Enabled = value; }  
   }  
   ```  
  
8. 在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。  
  
## <a name="see-also"></a>请参阅  
 [教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)[开发活动](../../esb-toolkit/development-activities.md)