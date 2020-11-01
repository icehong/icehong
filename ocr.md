from cnstd import CnStd
from cnocr import CnOcr

std = CnStd()
cn_ocr = CnOcr()

box_info_list = std.detect('test.jpg')

for box_info in box_info_list:
    cropped_img = box_info['cropped_img']  # 检测出的文本框
    ocr_res = cn_ocr.ocr_for_single_line(cropped_img)
    print('ocr result: %s' % ''.join(ocr_res))
