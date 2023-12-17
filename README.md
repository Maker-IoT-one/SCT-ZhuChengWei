# SCT-ZhuChengWei
20231214-SCT-朱成伟-算法

处理异常图片
    dir_lit = os.listdir('./work/cat_12_train/')for list in dir_lit:    img_path=os.path.join('./work/cat_12_train/',list)    img=Image.open(img_path)    if img.mode != 'RGB':        img = img.convert('RGB')        img.save(img_path)        print(img_path)dir_lit = os.listdir('./work/cat_12_test/')for list in dir_lit:    img_path=os.path.join('./work/cat_12_test/',list)    img=Image.open(img_path)    if img.mode != 'RGB':        img = img.convert('RGB')        img.save(img_path)        print(img_path)

整理成paddlex数据格式
划分训练集验证集
数据增强

