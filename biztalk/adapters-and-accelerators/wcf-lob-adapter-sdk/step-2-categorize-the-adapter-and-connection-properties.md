---
title: 步骤 2： 对其进行分类的适配器和连接属性 |Microsoft 文档
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
ms.openlocfilehash: 6e9d49323695b1070a8065cf7a5e548e61fc5db9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226821"
---
# <a name="step-2-categorize-the-adapter-and-connection-properties"></a>步骤 2： 对其进行分类的适配器和连接属性
![步骤 2 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")  
  
 **完成时间：** 30 分钟  
  
 在此步骤中，您将更新**EchoAdapterBindingElement**和**EchoAdapterBindingElementExtensionElement**要分配给适配器和连接属性的类别的类。 通过这样做，属性按逻辑分组在中按类别[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具。 例如，如果你想**应用程序**， **EnableAuthentication**，和**主机名**属性以便在下显示**连接**类别如下所示，你需要将连接类别分配给每个应用程序、 EnableAuthentication 和主机名的属性。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")  
  
 同样，如果你想**InboundFileFilter**和**InboundFleSystemWatcherFolder**属性以便在下显示**入站**类别如下所示，你需要将入站的类别分配给每个。 如果你想**计数**和**EnableConnectionPooling**以便在下显示**杂项**类别中，你需要将杂项类别分配给每个。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")  
  
 请记住，你可以分配你选择的任何类别名称的属性。 在此示例中，由于 EnableConnnectionPooling 属性不属于任何其他类别中，我们将其分类为杂项 （杂项）。 有关 InboundFileFilter 属性，因为在此示例中，在入站处理期间使用它很将入站分配给属性，而不是杂项更为合适。 下面是为 echo 适配器完成自定义属性进行分类。  
  
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
  
 除了这些更改，你还修改的 Dispose 方法**EchoAdapterHandlerBase**。  
  
 有关由 echo 适配器中，公开了适配器属性，请参阅的适配器属性部分[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，必须完成[步骤 1： 使用 WCF LOB 适配器开发向导创建 Echo 适配器项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md)。 你还应熟悉`System.ServiceModel.Configuration.BindingElementExtensionElement`和`System.ServiceModel.Configuration.StandardBindingElement`类。  
  
## <a name="update-the-echoadapterhandlerbase-dispose-method"></a>更新 EchoAdapterHandlerBase Dispose 方法  
  
1.  在**解决方案资源管理器**，双击**EchoAdapterHandlerBase.cs**文件。  
  
2.  删除以下语句从**释放**方法：  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     修改后的方法应类似于以下形式：  
  
    ```csharp  
    protected virtual void Dispose(bool disposing)  
    {  
       //  
       //TODO: Implement Dispose. Override this method in respective Handler classes  
       //  
    }  
    ```  
  
## <a name="update-the-adapter-properties-class"></a>更新适配器属性类  
  
1.  在**解决方案资源管理器**，双击**EchoAdapterBindingElement.cs**文件。  
  
2.  在 Visual Studio 编辑器中，展开**自定义生成属性**区域。  
  
3.  若要将分配**杂项**类别与**计数**属性，将下面的单个语句添加到的开头**计数**实现。  
  
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
  
4.  若要将分配**杂项**类别与**EnableConnectionPooling**属性，将下面的单个语句添加到的开头**EnableConnectionPooling**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
5.  若要将分配**入站**类别与**InboundFileFilter**属性，将下面的单个语句添加到的开头**InboundFileFilter**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
6.  若要将分配**入站**categoryto **inboundFleSystemWatcherFolder**属性，将下面的单个语句添加到的开头**inboundFleSystemWatcherFolder**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
7.  检查以确保中的代码**自定义生成属性**区域匹配以下：  
  
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
  
1.  在**解决方案资源管理器**，双击**EchoAdapterConnectionUri.cs**文件。  
  
2.  在 Visual Studio 编辑器中，展开**自定义生成属性**区域。  
  
3.  若要将分配**格式**类别与**EchoInUpperCase**属性，将下面的单个语句添加到的开头**EchoInUpperCase**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Format")]  
    ```  
  
4.  若要将分配**连接**类别与**主机名**属性，将下面的单个语句添加到的开头**主机名**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
5.  若要将分配**连接**类别与**应用程序**属性，将下面的单个语句添加到的开头**应用程序**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
6.  若要将分配**连接**categoryto **EnableAuthentication**属性，将下面的单个语句添加到的开头**EnableAuthentication**实现。  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
7.  检查以确保中的代码**自定义生成属性**区域匹配以下：  
  
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
  
8.  在 Visual Studio 中，从**文件**菜单上，单击**保存所有**。  
  
> [!NOTE]
>  保存所做的工作。 你可以安全地在此时关闭 Visual Studio 或转到下一步，[步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)。  
  
## <a name="what-did-i-just-do"></a>未我只需做什么？  
 你刚刚更新了要分配给由 echo 适配器公开每个适配器和连接属性的类别的类。  
  
## <a name="next-steps"></a>后续步骤  
 你实现连接、 元数据浏览、 搜索和解析功能和出站消息交换。 最后，生成并部署 echo 适配器。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)   
 [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)