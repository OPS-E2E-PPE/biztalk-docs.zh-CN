---
title: 第 2 步：适配器和连接属性进行分类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45b3dc64-2078-4008-878b-501f727f4a11
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d0d618d2e02e04b69e054c473b4a8b817cb52b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363342"
---
# <a name="step-2-categorize-the-adapter-and-connection-properties"></a>第 2 步：适配器和连接属性进行分类
![步骤 2 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")  
  
 **若要完成的时间：** 30 分钟  
  
 在此步骤中，你将更新**EchoAdapterBindingElement**并**EchoAdapterBindingElementExtensionElement**类，以向您的适配器和连接属性分配一个类别。 通过这样做，属性以逻辑方式按类别分组中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具。 例如，如果你想**应用程序**， **EnableAuthentication**，并**主机名**属性，以显示下**连接**类别，如下所示，您需要将连接类别分配给每个应用程序、 EnableAuthentication 和主机名的属性。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")  
  
 同样，如果你想**InboundFileFilter**并**InboundFleSystemWatcherFolder**属性，以显示下**入站**类别，如下所示，你需要将入站的类别分配给每个。 如果你想**计数**并**EnableConnectionPooling**显示下方**杂项**类别中，您需要为每个分配的杂项类别。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")  
  
 请记住，您可以分配你选择的任何类别名称的属性。 在此示例中，由于 EnableConnnectionPooling 属性不属于任何其他类别，因此我们归类为杂项 （其他）。 关于 InboundFileFilter 属性，因为在此示例中，在入站处理期间使用它就更适合要分配给属性，而不是其他入站。 下面是 echo 适配器的完成自定义属性分类。  
  
|**属性**|**类别**|  
|------------------|------------------|  
|InboundFileFilter|入站|  
|InboundFileSystemWatcherFolder|入站|  
|Count|杂项|  
|EnableConnectionPooling|杂项|  
|应用程序|连接|  
|EnableAuthentication|连接|  
|Hostname|连接|  
|EchoInUpperCase|格式|  
  
 除了这些更改，还修改的 Dispose 方法**EchoAdapterHandlerBase**。  
  
 有关公开 echo 适配器的适配器属性，请参阅适配器属性部分的[教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，必须完成[步骤 1:使用 WCF LOB 适配器开发向导创建 Echo 适配器项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md)。 您还应熟悉`System.ServiceModel.Configuration.BindingElementExtensionElement`和`System.ServiceModel.Configuration.StandardBindingElement`类。  
  
## <a name="update-the-echoadapterhandlerbase-dispose-method"></a>更新 EchoAdapterHandlerBase Dispose 方法  
  
1.  在中**解决方案资源管理器**，双击**EchoAdapterHandlerBase.cs**文件。  
  
2.  删除以下语句从**Dispose**方法：  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     修改后的方法应类似于下面所示：  
  
    ```csharp  
    protected virtual void Dispose(bool disposing)  
    {  
       //  
       //TODO: Implement Dispose. Override this method in respective Handler classes  
       //  
    }  
    ```  
  
## <a name="update-the-adapter-properties-class"></a>更新适配器属性类  
  
1.  在中**解决方案资源管理器**，双击**EchoAdapterBindingElement.cs**文件。  
  
2.  在 Visual Studio 编辑器中，展开**自定义生成的属性**区域。  
  
3.  若要将分配**杂项**到类别**计数**属性的开头添加下面的单个语句**计数**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
     **计数**实现现在应匹配以下内容：  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
    ```  
  
4.  若要将分配**杂项**到类别**EnableConnectionPooling**属性的开头添加下面的单个语句**EnableConnectionPooling**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
5.  若要将分配**入站**到类别**InboundFileFilter**属性的开头添加下面的单个语句**InboundFileFilter**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
6.  若要将分配**入站**categoryto **inboundFleSystemWatcherFolder**属性的开头添加下面的单个语句**inboundFleSystemWatcherFolder**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
7.  检查以确保中的代码**自定义生成的属性**区域匹配以下：  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("enableConnectionPooling", DefaultValue = true)]  
    public bool EnableConnectionPooling  
    {  
        get  
        {  
            return ((bool)(base["EnableConnectionPooling"]));  
        }  
        set  
        {  
            base["EnableConnectionPooling"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileFilter", DefaultValue = "*.txt")]  
    public string InboundFileFilter  
    {  
        get  
        {  
            return ((string)(base["InboundFileFilter"]));  
        }  
        set  
        {  
            base["InboundFileFilter"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileSystemWatcherFolder", DefaultValue = "{InboundFileSystemWatcherFolder}")]  
    public string InboundFileSystemWatcherFolder  
    {  
        get  
        {  
            return ((string)(base["InboundFileSystemWatcherFolder"]));  
        }  
        set  
        {  
            base["InboundFileSystemWatcherFolder"] = value;  
        }  
    }  
  
    #endregion Custom Generated Properties  
    ```  
  
## <a name="update-the-connection-properties"></a>更新连接属性  
  
1.  在中**解决方案资源管理器**，双击**EchoAdapterConnectionUri.cs**文件。  
  
2.  在 Visual Studio 编辑器中，展开**自定义生成的属性**区域。  
  
3.  若要将分配**格式**到类别**EchoInUpperCase**属性的开头添加下面的单个语句**EchoInUpperCase**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Format")]  
    ```  
  
4.  若要将分配**连接**到类别**主机名**属性的开头添加下面的单个语句**主机名**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
5.  若要将分配**连接**到类别**应用程序**属性的开头添加下面的单个语句**应用程序**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
6.  若要将分配**连接**categoryto **EnableAuthentication**属性的开头添加下面的单个语句**EnableAuthentication**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
7.  检查以确保中的代码**自定义生成的属性**区域匹配以下：  
  
    ```csharp  
    #region Custom Generated Properties  
            [System.ComponentModel.Category("Format")]  
            public bool EchoInUpperCase  
            {  
                get  
                {  
                    return this.echoInUpperCase;  
                }  
                set  
                {  
                    this.echoInUpperCase = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Hostname  
            {  
                get  
                {  
                    return this.hostname;  
                }  
                set  
                {  
                    this.hostname = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Application  
            {  
                get  
                {  
                    return this.application;  
                }  
                set  
                {  
                    this.application = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public bool EnableAuthentication  
            {  
                get  
                {  
                    return this.enableAuthentication;  
                }  
                set  
                {  
                    this.enableAuthentication = value;  
                }  
            }  
            #endregion Custom Generated Properties  
    ```  
  
8.  在 Visual Studio 中，从**文件**菜单上，单击**全部保存**。  
  
> [!NOTE]
>  保存所做的工作。 可以安全地关闭 Visual Studio 或转到下一步，[步骤 3:实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 你刚刚更新了类，以向公开 echo 适配器的每个适配器和连接属性分配一个类别。  
  
## <a name="next-steps"></a>后续步骤  
 您实现连接、 元数据浏览、 搜索和解析功能和出站消息交换。 最后，您生成并部署 echo 适配器。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)   
 [教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)