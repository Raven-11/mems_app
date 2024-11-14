#### Error: Qt6Gui could not be found because dependency WrapOpenGL could not be found. 
	sudo apt install libglx-dev libgl1-mesa-dev
	
#### Error: Qt:Mqtt target not found
(https://embeddedlaboratory.blogspot.com/2023/01/getting-started-with-mqtt-using-qt.html)


	create *Qt_environment.sh*:
	export QT_VERSION="6.7.2"
	export QT_INSTALL_DIR="/home/sonnh/Qt"
	export CMAKE_BIN_DIR="${QT_INSTALL_DIR}/Tools/CMake/bin"
	export QMAKE_BIN_DIR="${QT_INSTALL_DIR}/${QT_VERSION}/gcc_64/bin"
	export CMAKE_PREFIX_PATH="${QT_INSTALL_DIR}/${QT_VERSION}/gcc_64/"
	export NINJA_DIR="${QT_INSTALL_DIR}/Tools/Ninja"
	export PATH="${PATH}:${CMAKE_BIN_DIR}:${QMAKE_BIN_DIR}:${NINJA_DIR}"
	
	git clone https://code.qt.io/qt/qtmqtt.git
	cd qtmqtt
	git checkout 6.7.2
	source Qt_Environment.sh 
	mkdir build && cd build
	/home/sonnh/Qt/6.7.2/gcc_arm64/bin/qt-configure-module ..
	/home/sonnh/Qt/Tools/CMake/bin/cmake --build .
	/home/sonnh/Qt/Tools/CMake/bin/cmake --install . --verbose


#### Error: missing Ninja
	sudo apt install ninja-build

