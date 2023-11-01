# a21-particle-effects
 This is the regex<br />
Find:<br />
([p_[0-9a-z]*).prefab<br />
Replace:<br />
<item name="vuxParticle-$1">
			<property name="Extends" value="vuxParticleMaster" param1="DescriptionKey"/>
			<effect_group name="Display">
				<triggered_effect trigger="onSelfPrimaryActionUpdate" action="AddPart" part="RightHand" prefab="ParticleEffects/$1" parentTransform="RightHand" localPos="0,0,0" localRot="0,0,0"/>
				<triggered_effect trigger="onSelfPrimaryActionUpdate" action="SetTransformActive" active="false" transform_path="ProjectileJoint"/>
				<triggered_effect trigger="onSelfPrimaryActionUpdate" action="SetTransformActive" active="false" transform_path="crossbow_mesh"/>
				<triggered_effect trigger="onSelfEquipStop" action="RemovePart" part="RightHand"/>
				<triggered_effect trigger="onSelfEquipStop" action="SetTransformActive" active="true" transform_path="ProjectileJoint"/>
				<triggered_effect trigger="onSelfEquipStop" action="SetTransformActive" active="true" transform_path="crossbow_mesh"/>
			</effect_group>
		</item>
