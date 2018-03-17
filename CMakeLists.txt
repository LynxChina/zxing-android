cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-multichar -D_ANDROID  -DBUILDING_LIBICONV -DBUILDING_LIBCHARSET -DIN_LIBRARY")
#set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/so/${ANDROID_ABI})
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

add_definitions(-DLIBDIR="c")

add_library(
    zxing

    SHARED

    src/main/jni/bigint/BigInteger.cc
    src/main/jni/bigint/BigInteger.cc
    src/main/jni/bigint/BigIntegerAlgorithms.cc
    src/main/jni/bigint/BigIntegerAlgorithms.cc
    src/main/jni/bigint/BigIntegerUtils.cc
    src/main/jni/bigint/BigIntegerUtils.cc
    src/main/jni/bigint/BigUnsigned.cc
    src/main/jni/bigint/BigUnsigned.cc
    src/main/jni/bigint/BigUnsignedInABase.cc
    src/main/jni/bigint/BigUnsignedInABase.cc
    src/main/jni/zxing/aztec/AztecDetectorResult.cpp
    src/main/jni/zxing/aztec/AztecReader.cpp
    src/main/jni/zxing/aztec/decoder/Decoder.cpp
    src/main/jni/zxing/aztec/detector/Detector.cpp
    src/main/jni/zxing/BarcodeFormat.cpp
    src/main/jni/zxing/Binarizer.cpp
    src/main/jni/zxing/BinaryBitmap.cpp
    src/main/jni/zxing/ChecksumException.cpp
    src/main/jni/zxing/common/BitArray.cpp
    src/main/jni/zxing/common/BitArrayIO.cpp
    src/main/jni/zxing/common/BitMatrix.cpp
    src/main/jni/zxing/common/BitSource.cpp
    src/main/jni/zxing/common/CharacterSetECI.cpp
    src/main/jni/zxing/common/DecoderResult.cpp
    src/main/jni/zxing/common/detector/MonochromeRectangleDetector.cpp
    src/main/jni/zxing/common/detector/WhiteRectangleDetector.cpp
    src/main/jni/zxing/common/DetectorResult.cpp
    src/main/jni/zxing/common/GlobalHistogramBinarizer.cpp
    src/main/jni/zxing/common/GreyscaleLuminanceSource.cpp
    src/main/jni/zxing/common/GreyscaleRotatedLuminanceSource.cpp
    src/main/jni/zxing/common/GridSampler.cpp
    src/main/jni/zxing/common/HybridBinarizer.cpp
    src/main/jni/zxing/common/IllegalArgumentException.cpp
    src/main/jni/zxing/common/PerspectiveTransform.cpp
    src/main/jni/zxing/common/reedsolomon/GenericGF.cpp
    src/main/jni/zxing/common/reedsolomon/GenericGFPoly.cpp
    src/main/jni/zxing/common/reedsolomon/ReedSolomonDecoder.cpp
    src/main/jni/zxing/common/reedsolomon/ReedSolomonException.cpp
    src/main/jni/zxing/common/Str.cpp
    src/main/jni/zxing/common/StringUtils.cpp
    src/main/jni/zxing/datamatrix/DataMatrixReader.cpp
    src/main/jni/zxing/datamatrix/decoder/BitMatrixParser.cpp
    src/main/jni/zxing/datamatrix/decoder/DataBlock.cpp
    src/main/jni/zxing/datamatrix/decoder/DecodedBitStreamParser.cpp
    src/main/jni/zxing/datamatrix/decoder/Decoder.cpp
    src/main/jni/zxing/datamatrix/detector/CornerPoint.cpp
    src/main/jni/zxing/datamatrix/detector/Detector.cpp
    src/main/jni/zxing/datamatrix/detector/DetectorException.cpp
    src/main/jni/zxing/datamatrix/Version.cpp
    src/main/jni/zxing/DecodeHints.cpp
    src/main/jni/zxing/Exception.cpp
    src/main/jni/zxing/FormatException.cpp
    src/main/jni/zxing/InvertedLuminanceSource.cpp
    src/main/jni/zxing/LuminanceSource.cpp
    src/main/jni/zxing/multi/ByQuadrantReader.cpp
    src/main/jni/zxing/multi/GenericMultipleBarcodeReader.cpp
    src/main/jni/zxing/multi/MultipleBarcodeReader.cpp
    src/main/jni/zxing/multi/qrcode/detector/MultiDetector.cpp
    src/main/jni/zxing/multi/qrcode/detector/MultiFinderPatternFinder.cpp
    src/main/jni/zxing/multi/qrcode/QRCodeMultiReader.cpp
    src/main/jni/zxing/MultiFormatReader.cpp
    src/main/jni/zxing/oned/CodaBarReader.cpp
    src/main/jni/zxing/oned/Code128Reader.cpp
    src/main/jni/zxing/oned/Code39Reader.cpp
    src/main/jni/zxing/oned/Code93Reader.cpp
    src/main/jni/zxing/oned/EAN13Reader.cpp
    src/main/jni/zxing/oned/EAN8Reader.cpp
    src/main/jni/zxing/oned/ITFReader.cpp
    src/main/jni/zxing/oned/MultiFormatOneDReader.cpp
    src/main/jni/zxing/oned/MultiFormatUPCEANReader.cpp
    src/main/jni/zxing/oned/OneDReader.cpp
    src/main/jni/zxing/oned/OneDResultPoint.cpp
    src/main/jni/zxing/oned/UPCAReader.cpp
    src/main/jni/zxing/oned/UPCEANReader.cpp
    src/main/jni/zxing/oned/UPCEReader.cpp
    src/main/jni/zxing/pdf417/decoder/BitMatrixParser.cpp
    src/main/jni/zxing/pdf417/decoder/DecodedBitStreamParser.cpp
    src/main/jni/zxing/pdf417/decoder/Decoder.cpp
    src/main/jni/zxing/pdf417/decoder/ec/ErrorCorrection.cpp
    src/main/jni/zxing/pdf417/decoder/ec/ModulusGF.cpp
    src/main/jni/zxing/pdf417/decoder/ec/ModulusPoly.cpp
    src/main/jni/zxing/pdf417/detector/Detector.cpp
    src/main/jni/zxing/pdf417/detector/LinesSampler.cpp
    src/main/jni/zxing/pdf417/PDF417Reader.cpp
    src/main/jni/zxing/qrcode/decoder/BitMatrixParser.cpp
    src/main/jni/zxing/qrcode/decoder/DataBlock.cpp
    src/main/jni/zxing/qrcode/decoder/DataMask.cpp
    src/main/jni/zxing/qrcode/decoder/DecodedBitStreamParser.cpp
    src/main/jni/zxing/qrcode/decoder/Decoder.cpp
    src/main/jni/zxing/qrcode/decoder/Mode.cpp
    src/main/jni/zxing/qrcode/detector/AlignmentPattern.cpp
    src/main/jni/zxing/qrcode/detector/AlignmentPatternFinder.cpp
    src/main/jni/zxing/qrcode/detector/Detector.cpp
    src/main/jni/zxing/qrcode/detector/FinderPattern.cpp
    src/main/jni/zxing/qrcode/detector/FinderPatternFinder.cpp
    src/main/jni/zxing/qrcode/detector/FinderPatternInfo.cpp
    src/main/jni/zxing/qrcode/ErrorCorrectionLevel.cpp
    src/main/jni/zxing/qrcode/FormatInformation.cpp
    src/main/jni/zxing/qrcode/QRCodeReader.cpp
    src/main/jni/zxing/qrcode/Version.cpp
    src/main/jni/zxing/Reader.cpp
    src/main/jni/zxing/Result.cpp
    src/main/jni/zxing/ResultIO.cpp
    src/main/jni/zxing/ResultPoint.cpp
    src/main/jni/zxing/ResultPointCallback.cpp
    src/main/jni/zxing/MatSource.cpp
)

set(libs "${CMAKE_SOURCE_DIR}/src/main/jni")

add_library(opencv SHARED IMPORTED)
set_target_properties(opencv PROPERTIES
    IMPORTED_LOCATION "${libs}/opencv/lib/${ANDROID_ABI}/libopencv_java3.so")

add_library(iconv SHARED IMPORTED)
set_target_properties(iconv PROPERTIES
    IMPORTED_LOCATION "${libs}/iconv/lib/${ANDROID_ABI}/libiconv.so")

include_directories(
    src/main/jni/include
    src/main/jni/include/bigint
    src/main/jni/opencv/include
    src/main/jni/iconv/include
)

target_link_libraries(
    zxing

    opencv
    iconv
)