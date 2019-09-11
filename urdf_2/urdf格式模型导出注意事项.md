# urdf格式模型导出注意事项

edited by ps 2019/09/11

##  前期建模准备

注意关节原点与零件局部零点相同，建议使用sw重新建立简化仿真模型。而不是导入复杂网格

定义关节关系后可使用urdf插件自动生成坐标

转动关节配合时使用面与面装配，使用边线装配可能出现无法生成坐标情况

导出为urdf与网格

装配体关节初始位置即为导出关节0位置，预先应定义完成初始位置

完成初始位置约束后需删除角度与平行配合，否则插件无法自动生成转动轴

## urdf文件修改

.launch文件将"gui"默认“false"改为"true",开启关节控制面板

rviz中修改world cod为base link, 需手动add robot model

工作空间可直接catkin_make

catkin_make->source devel/setup.bash->cd src/model name/launch->roslaunch display/gazebo.launch